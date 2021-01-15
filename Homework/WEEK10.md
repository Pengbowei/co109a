# Homework WEEK10

## fill

* CODE

<pre><code>// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/04/Fill.asm

// Runs an infinite loop that listens to the keyboard input.
// When a key is pressed (any key), the program blackens the screen,
// i.e. writes "black" in every pixel;
// the screen should remain fully black as long as the key is pressed. 
// When no key is pressed, the program clears the screen, i.e. writes
// "white" in every pixel;
// the screen should remain fully clear as long as no key is pressed.

// Put your code here.
(RESTART)
@SCREEN
D=A 
@0
M=D	//將SCREEN起始位置存入RAM[0]

///////////////////////////
(KBDCHECK)

@KBD
D=M
@BLACK
D;JGT	//如果按下KBD任何鍵JUMP TO BLACK
@WHITE
D;JEQ	//否則 TIMP TO WHITE

@KBDCHECK
0;JMP
///////////////////////////
(BLACK)
@1
M=-1	//螢幕反黑
@CHANGE
0;JMP

(WHITE)
@1
M=0	//螢幕反白
@CHANGE
0;JMP
//////////////////////////
(CHANGE)
@1	//檢查螢幕式黑色還是白色
D=M	//暫存器保存現在螢幕的值

@0
A=M	//取得螢幕pixel位置
M=D	//反黑或反白

@0
D=M+1	//INC TO NEXT PIXEL
@KBD
D=A-D	//KBD-SCREEN=A

@0
M=M+1	//INC TO NEXT PIXEL
A=M

@CHANGE
D;JGT	//IF A=0 EXIT AS THE WHOLE SCREEN IS BLACK
/////////////////////////
@RESTART
0;JMP</code></pre>