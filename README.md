# 台大程設
## globals() locals()讓變數名稱跟著迴圈動態定義
```
Python
lst = ['A','B','C']
lst2 = []
for i in range(len(lst)):
    globals()['No.'+ str(i) ] = list(lst[i])
    lst2 += str(lst[i])
    print(globals()['No.'+str(i) ],lst2)
```
它在執行就可以設出變數 `No.1` 並且 `= ['A']` (因為這裡也使用了 `list()` 去設串列)  
依序還會有  
`No.2 = ['B']`  
`No.3 = ['C']`  

而這段程式碼的輸出就是
```
['A'] ['A']
['B'] ['A', 'B']
['C'] ['A', 'B', 'C']
```
沒錯，就是醬!
