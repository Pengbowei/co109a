# Homework WEEK6

## 1.Bit

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/03/a/Bit.hdl

/**
 * 1-bit register:
 * If load[t] == 1 then out[t+1] = in[t]
 *                 else out does not change (out[t+1] = out[t])
 */

CHIP Bit {
    IN in, load;
    OUT out;

    PARTS:
    // Put your code here:
    Mux(a=outT , b=in , sel=load , out=muxO);
    DFF(in=muxO , out=out , out=outT);
}
</code></pre>

* 當時間為t時load為1，輸出為in的t-1。否則為out的t-1。故使用Mux! a為out[t-1] b為in[t]

## 2.Register

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/03/a/Register.hdl

/**
 * 16-bit register:
 * If load[t] == 1 then out[t+1] = in[t]
 * else out does not change
 */

CHIP Register {
    IN in[16], load;
    OUT out[16];

    PARTS:
    // Put your code here:
    Bit(in=in[0] , load=load , out=out[0]);
    Bit(in=in[1] , load=load , out=out[1]);
    Bit(in=in[2] , load=load , out=out[2]);
    Bit(in=in[3] , load=load , out=out[3]);
    Bit(in=in[4] , load=load , out=out[4]);
    Bit(in=in[5] , load=load , out=out[5]);
    Bit(in=in[6] , load=load , out=out[6]);
    Bit(in=in[7] , load=load , out=out[7]);
    Bit(in=in[8] , load=load , out=out[8]);
    Bit(in=in[9] , load=load , out=out[9]);
    Bit(in=in[10] , load=load , out=out[10]);
    Bit(in=in[11] , load=load , out=out[11]);
    Bit(in=in[12] , load=load , out=out[12]);
    Bit(in=in[13] , load=load , out=out[13]);
    Bit(in=in[14] , load=load , out=out[14]);
    Bit(in=in[15] , load=load , out=out[15]);
}
</code></pre>

* Register為16個Bit所構成

## 本週心得
* 這週的習題不算太難，我也上網去了解了解D型正反器的構造及原理。
* D型正反器為一個輸入，一個輸出以及一個時脈輸入，當時賣輸入由0轉為1時，輸出就會等於輸入。