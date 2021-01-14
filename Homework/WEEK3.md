# Homework WEEK3

## 1.HalfAdder

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/02/HalfAdder.hdl

/**
 * Computes the sum of two bits.
 */

CHIP HalfAdder {
    IN a, b;    // 1-bit inputs
    OUT sum,    // Right bit of a + b 
        carry;  // Left bit of a + b

    PARTS:
    // Put you code here:
    Xor(a=a , b=b , out=sum);
    And(a=a , b=b , out=carry);
}
</code></pre>

## 2.FullAdder

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/02/FullAdder.hdl

/**
 * Computes the sum of three bits.
 */

CHIP FullAdder {
    IN a, b, c;  // 1-bit inputs
    OUT sum,     // Right bit of a + b + c
        carry;   // Left bit of a + b + c

    PARTS:
    // Put you code here:
    HalfAdder(a=a , b=b , sum=ab , carry=cab);
    HalfAdder(a=c , b=ab , sum=sum , carry=acab);
    Or(a=cab , b=acab , out=carry);
}</code></pre>

## 3.Add16

* CODE
<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/02/Adder16.hdl

/**
 * Adds two 16-bit values.
 * The most significant carry bit is ignored.
 */

CHIP Add16 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
   // Put you code here:
   FullAdder(a=a[0] , b=b[0] , c=false , sum=out[0] , carry=c0);
   FullAdder(a=a[1] , b=b[1] , c=c0 , sum=out[1] , carry=c1);
   FullAdder(a=a[2] , b=b[2] , c=c1 , sum=out[2] , carry=c2);
   FullAdder(a=a[3] , b=b[3] , c=c2 , sum=out[3] , carry=c3);
   FullAdder(a=a[4] , b=b[4] , c=c3 , sum=out[4] , carry=c4);
   FullAdder(a=a[5] , b=b[5] , c=c4 , sum=out[5] , carry=c5);
   FullAdder(a=a[6] , b=b[6] , c=c5 , sum=out[6] , carry=c6);
   FullAdder(a=a[7] , b=b[7] , c=c6 , sum=out[7] , carry=c7);
   FullAdder(a=a[8] , b=b[8] , c=c7 , sum=out[8] , carry=c8);
   FullAdder(a=a[9] , b=b[9] , c=c8 , sum=out[9] , carry=c9);
   FullAdder(a=a[10] , b=b[10] , c=c9 , sum=out[10] , carry=c10);
   FullAdder(a=a[11] , b=b[11] , c=c10 , sum=out[11] , carry=c11);
   FullAdder(a=a[12] , b=b[12] , c=c11 , sum=out[12] , carry=c12);
   FullAdder(a=a[13] , b=b[13] , c=c12 , sum=out[13] , carry=c13);
   FullAdder(a=a[14] , b=b[14] , c=c13 , sum=out[14] , carry=c14);
   FullAdder(a=a[15] , b=b[15] , c=c14 , sum=out[15] , carry=c15);
}</code></pre>

## 4. Inc16

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/02/Inc16.hdl

/**
 * 16-bit incrementer:
 * out = in + 1 (arithmetic addition)
 */

CHIP Inc16 {
    IN in[16];
    OUT out[16];

    PARTS:
   // Put you code here:
   HalfAdder(a=in[0] , b=true , sum=out[0] , carry=c0);
   HalfAdder(a=in[1] , b=c0 , sum=out[1] , carry=c1);
   HalfAdder(a=in[2] , b=c1 , sum=out[2] , carry=c2);
   HalfAdder(a=in[3] , b=c2 , sum=out[3] , carry=c3);
   HalfAdder(a=in[4] , b=c3 , sum=out[4] , carry=c4);
   HalfAdder(a=in[5] , b=c4 , sum=out[5] , carry=c5);
   HalfAdder(a=in[6] , b=c5 , sum=out[6] , carry=c6);
   HalfAdder(a=in[7] , b=c6 , sum=out[7] , carry=c7);
   HalfAdder(a=in[8] , b=c7 , sum=out[8] , carry=c8);
   HalfAdder(a=in[9] , b=c8 , sum=out[9] , carry=c9);
   HalfAdder(a=in[10] , b=c9 , sum=out[10] , carry=c10);
   HalfAdder(a=in[11] , b=c10 , sum=out[11] , carry=c11);
   HalfAdder(a=in[12] , b=c11 , sum=out[12] , carry=c12);
   HalfAdder(a=in[13] , b=c12 , sum=out[13] , carry=c13);
   HalfAdder(a=in[14] , b=c13 , sum=out[14] , carry=c14);
   HalfAdder(a=in[15] , b=c14 , sum=out[15] , carry=c15);
}</code></pre>

## 本週心得

* 半加器為兩個輸入以及兩個輸出，兩個輸出分別為相加後(使用XOR閘來構成)的值以及進位(使用AND閘來構成)的值。
* 全加器為三個輸入以及兩個輸出，使用兩個半加器構成。兩個輸入為被加數，另外一個輸入為前一組被加數的進位值。兩個輸出分別為相加後的值以及進位的值。
* 加法器(16bits)為16個全加器結合而成，三個輸入以及兩個輸出，兩個輸入為兩個被加數，另外一個輸入為前一組bit相加的進位值(in[0]時設為false)。兩個輸出分別為相加後的值以及進位的值。
* 遞增器為16個半加器組合而成，網路上也有人使用16個全加器組合而成，但我實在還不太了解這個閘的功能以及用途...