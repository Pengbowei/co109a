# 資工二 彭柏瑋 110810531 - 期末總整理

欄位 | 內容
-----|--------
學期 | 109 學年度上學期
學生 |  彭柏瑋
學號末兩碼 | 31
教師 | [陳鍾誠](https://www.nqu.edu.tw/educsie/index.php?act=blog&code=list&ids=4)
學校科系 | [金門大學資訊工程系](https://www.nqu.edu.tw/educsie/index.php)
課程內容 | https://gitlab.com/ccc109/co

# 習題(每周心得皆整理再連結下)
* 課程筆記則放在各作業中
## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEE1.md'>第1周</a>
* 覺得滿厲害的一堂課，最後還可以自己設計Computer
* 這週設計了最基本的六個電路閘

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK2.md'>第2周</a>
* 這週學到的閘為上週的進階版，閘的輸入不再是1bit而進入到了16bits
* Mux和DMux中的Way為有幾個輸入或輸出，sel所需的bit則由幾個Way決定

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK4.md'>第4周</a>
* 半加器為兩個輸入以及兩個輸出，兩個輸出分別為相加後(使用XOR閘來構成)的值以及進位(使用AND閘來構成)的值。
* 全加器為三個輸入以及兩個輸出，使用兩個半加器構成。兩個輸入為被加數，另外一個輸入為前一組被加數的進位值。兩個輸出分別為相加後的值以及進位的值。
* 加法器(16bits)為16個全加器結合而成，三個輸入以及兩個輸出，兩個輸入為兩個被加數，另外一個輸入為前一組bit相加的進位值(in[0]時設為false)。兩個輸出分別為相加後的值以及進位的值。
* 遞增器為16個半加器組合而成，網路上也有人使用16個全加器組合而成，但我實在還不太了解這個閘的功能以及用途...

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK5.md'>第5周</a>
* 再實作的當下不太了解ng以及zr的作用，是參考了網路上的程式碼才寫出來的，當要去描述程式的設計原理時才上網去找他們的功能，理解後才發現原理非常的簡單，若再實作的當下能夠及時去查詢的話就更加的去了解這個電路閘的細節了

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK6.md'>第6周</a>
* 這週的習題不算太難，我也上網去了解了解D型正反器的構造及原理。
* D型正反器為一個輸入，一個輸出以及一個時脈輸入，當時賣輸入由0轉為1時，輸出就會等於輸入。

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK7.md'>第7周</a>
* 這週的習題原理都相同，能夠寫出RAM8後面的習題就不是問題，就只是組成的單元稍有不同，以及address的第幾個bit需要注意而已!!

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK8.md'>第8周</a>
* PC設計原理與上個單元的ALU相似，但控制上有分先後順序，若順序錯了程式就無法順利執行!

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK9.md'>第9周</a>
* 這周遇到了一點障礙，語法不習慣導致沒有辦法順利地寫出程式。
* 參考網址:https://github.com/FUYUHSUAN/co109a/blob/master/homework/HW8(9week).md

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK10.md'>第10周</a>


## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK11.md'>第11周</a>
* 這週的習題為螢幕和鍵盤對暫存器的關係，程式比之前的複雜多，難度以更難了。

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK12.md'>第12周</a>
* instruction的控制需要非常清楚，每個Bit都有其控制的閘。

## <a href='https://github.com/Pengbowei/co109a/blob/master/Homework/WEEK13.md'>第13周</a>



