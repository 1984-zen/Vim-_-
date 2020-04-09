# Vim筆記
技巧18-22
### 基本操作 
|指令 |意義 |
| -------- |  -------- |
|f{char}|跳到当前行的某个字符上|
|;和,|正向或反向的跳至剛剛搜尋的字符上|
|s|刪除該字符並切換到Insert模式|
|S|刪除整行並切換到Insert模式|
|c2w刪除兩個字|c可以刪除一個字，並進入到插入模式||
|viw|進入Visual模式並且選取該詞|
|daw|剪下一個字|
|yaw|複製一個字|
|p/P|貼游標後/貼游標前|
|A|游標移到該行末，進入到Insert模式|
|a|修改游標後，進入到Insert模式|
|I|游標移到該行頭，進入到Insert模式|
|i|修改游標前，進入到Insert模式|
|Insert模式control+w|刪除至上個單字的開頭|
|Insert模式control+u|刪除上個行首|
|G|文件結尾|
---

### 插入模式|--插入字符編碼 
| 指令|意義 |進制|
| -------- |  -------- | -------- |
| <C-v>065|插入大写字母“A” |10(位數)|
| <C-v>u00bf|插入字符编码为 00bf 的反转问号(“¿”)|16|
| <C-k>?I |插入反转问号(“¿”)用二合字母||
----

### Normal模式|--得知字符的编码
| 指令|意義 |
| -------- |  -------- |
|ga|得知字符的编码|

----
### 替換模式|--R
| 指令|意義 |
| -------- |  -------- |
|按R切換到替換模式，或是鍵盤上的<Insert>也可切換|想直接取代原本位置的字符，完成替換後ESC退回到Normal模式|
|按r切換到替換模式，輸入字符替換|想直接取代原本位置的字符，覆盖一个字符，之后马上又回到普通模式|
|虚拟替换模式gR或gr|不同在於他會按屏幕上实际显示的宽度来替换字符的，而不是按文 件中所保存的字符进行替换|
----
### Visual模式下的3個子模式
| 模式 | 指令 |
| -------- |  -------- |
|v|面向字，一個一個字選取|
|V|面向行，直接選取一行|
|<C-v>|面向列块，選取列|
|gv|重新選取上次的範圍|
|o|可以按下o重新調整選區的端點，搭配b前一個字首，以及e跳到下一個字尾|
----
### Visual模式|--選取後--縮排
|指令| 意義 | 
| -------- |  -------- |
|>|向內縮排 |
|<|向外縮排 |
> 若想要一次到位縮排兩個tab可以指令：2>
> 設定縮排指令:set shiftwidth=4 softtabstop=4 expandtab

技巧23-33
### Normal模式|--選取HTML中Tag裡面的文字
| 意義 | 指令 |
| -------- |  -------- |
|inside tag選中tag中的文字|vit|

### Visual模式|--英文小寫轉大寫
|指令| 意義 |
| -------- |  -------- |
|U|英文小寫轉大(.只轉同數量的大寫)|
> 若要裡面的英文轉成大寫可以在文字被選取後按`U`就可以轉成大寫並從Visual模式轉回到Normal模式

### Nomal模式|--英文小寫轉大寫
| 意義 | 指令 |
| -------- |  -------- |
|英文小寫轉大(.不限數量都轉大寫)|gUit|
> 操作符(gU)+動作命令(it)

### Insert模式|--命令隨時做運算
| 意義 | 指令 |
| -------- |  -------- |
|操作數學運算|control+r|

### EX指令|--跳到指定行數
| 指令 | 意義 |
| -------- |  -------- |
|跳到指定行|:number|
|跳到最後一行|:$|

### Normal模式|--跳到指定行數
| 指令 | 意義 |
| -------- |  -------- |
|number+G|跳到指定number行|

### EX指令|--替換每一行的文字
| 指令 | 意義 |
| -------- |  -------- |
|%s/Practical/Pragmatic/| 把每一行內的第一個Practical替換為Pragmatic|
|%| 所有行|

### Visual模式|--選取某一行以下的所有範圍
| 指令 | 意義 |
| -------- |  -------- |
|2G|游標跳到第2行
|VG| 選取某一行以下的所有範圍 |

### EX指令|--選取範圍
| 指令 | 意義 |
| -------- |  -------- |
|:/<html>/,/<\/html>/p|選取開頭是<html>結尾是</html>|
|VG| 選取某一行以下的所有範圍 |
|:/<html>/+1,/<\/html>/-1p|修正選取偏移|
|.,.+3p|選取當前行到往下3行|
|:6copy.|把第6行複製，並貼到當前行下方|

### EX指令|--複製行
| 指令 | 意義 |
| -------- |  -------- |
|:6t.|把第 6 行复制到当前行下方|
|:t6:|把当前行复制到第 6 行下方|
|:t.|为当前行创建一个副本(类似于普通模式下的 yyp)|
|:t$|把当前行复制到文本结尾|
|:'<,'>t0|把高亮选中的行复制到文件开头|

### EX指令|--移動行
| 指令 | 意義 |
| -------- |  -------- |
|V|複製行|
|:'<,'>m$|移動到最後一行|
|@:|重複上次EX指令動作|

### EX指令|--移動行
| 指令 | 意義 |
| -------- |  -------- |
|A;|在行末加上;|
|:'<,'>normal .|對選取區域的每一行，執行普通模式下的.命令|
|:%normal A;|同上的動作，更簡潔|

### EX指令|--重複執行
| 指令 | 意義 |
| -------- |  -------- |
|@:|重複執行，執行完@:後就可以用@@來重複執行|

### EX指令|--自動補全
| 指令 | 意義 |
| -------- |  -------- |
|<tab>按鍵|可以自動補全指令|
|<C-d>|可以提示指令|

### EX指令+Normal指令｜--自動補全
| 指令 | 意義 |
| -------- |  -------- |
|*|可以在游標停留的位置上的單字，按下*就可以跳到下一個同單字|
|cw|修改文字|
|:%s//<C-r><C-w>/g|在指令按下<C-r><C-w>會把游標停留上的單字複製到指令上面，即可以完成指令並執行全文替換成該單字|
|<C-r><C-a>|複製游標上單詞到指令行上|