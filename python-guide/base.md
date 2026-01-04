# Python 基礎語法
## 變數 (Variables)
### 變數就像是數學中的未知數，可以用來儲存資料。

    # 在萬物前面輸入井字號就會是一個註解，Python不會執行註解的內容，在colab中，你可以看到註解變成綠色的字
    
    # 將數字 10 存到變數 x
    x = 10
    
    # 將文字 "Hello" 存到變數 message
    message = "Hello, Python!"
    
    # 可以用 print() 函式印出變數的內容
    print(x)
    print(message)
    
    # 在colab介面中，按左上角的播放鍵或按 shift + enter 可以執行此區塊內的程式碼

## 串列 (Lists)
### 串列可以用來儲存一連串的資料，資料可以是數字、文字或其他任何東西。

    # 創建一個包含數字的串列
    numbers = [1, 2, 3, 4, 5]
    print(numbers)
    
    # 創建一個包含文字的串列
    names = ["Alice", "Bob", "Charlie"]
    print(names)
    
    # 取得串列中的特定元素 (注意：索引從 0 開始！)
    print(numbers[0]) # 印出 1
    print(names[1])   # 印出 Bob
    
    # 也可以建立多維串列 (串列中包含串列)
    data_group1 = [10.1, 10.3, 10.2]
    all_data = [[10.1, 10.3, 10.2], [12.5, 12.3, 12.7], [15.0, 15.1, 14.9]]
    print(all_data[0])      # 印出第一組數據 [10.1, 10.3, 10.2]
    print(all_data[0][1]) # 印出第一組數據的第二個值 10.3
    
    # 在colab介面中，按左上角的播放鍵或按shift + enter 可以執行此區塊內的程式碼

## 迴圈 (Loops)
### 迴圈可以讓我們重複執行相同的程式碼。for 迴圈常用來遍歷串列中的每一個元素。

    # 還記得numbers這個變數有哪些資料嗎?
    # 忘了也沒關係，colab會記得你在這個頁面所設的所有變數
    
    # 遍歷 numbers 串列中的每一個數字並印出
    for num in numbers:
        print(num)
    
    # 也可以搭配 range() 函式產生一連串數字
    for i in range(5): # range(5) 會產生 0, 1, 2, 3, 4
        print(i)
    
    # 在colab介面中，按左上角的播放鍵或按shift + enter 可以執行此區塊內的程式碼
