# Homework WEEK8 add

## PC

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/03/a/PC.hdl

/**
 * A 16-bit counter with load and reset control bits.
 * if      (reset[t] == 1) out[t+1] = 0
 * else if (load[t] == 1)  out[t+1] = in[t]
 * else if (inc[t] == 1)   out[t+1] = out[t] + 1  (integer addition)
 * else                    out[t+1] = out[t]
 */

CHIP PC {
    IN in[16],load,inc,reset;
    OUT out[16];

    PARTS:
    // Put your code here:
    Inc16(in=PC , out=inPC);
    Mux16(a=PC , b=inPC , sel=inc , out=outINC);
    Mux16(a=outINC , b=in , sel=load , out=outLOAD);
    Mux16(a=outLOAD , b=false , sel=reset , out=outRESET);
    Register(in=outRESET , load=true , out=PC , out=out);

}
</code></pre>

## 本週心得
* PC設計原理與上個單元的ALU相似，但控制上有分先後順序，若順序錯了程式就無法順利執行!