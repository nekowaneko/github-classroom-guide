# 矩陣、Numpy 陣列與迴歸線(Regression line)
### 做散佈圖最重要的是向人們闡述操縱變因與應變變因的關係，因此，需要用"迴歸線"來表達。

### 要計算迴歸線的相關參數，需要透過矩陣運算求得。

## 何謂矩陣
### 矩陣是由m行n列的「元素」所組成的矩形陣列。


### 你們在二年級下學期的數學就會學到，這邊可以先知道它是啥，也可以知道如何用程式算矩陣。
### 以下內容展示的是如何產生轉置矩陣

    # 在實際操作上，我們可以用簡單的程式碼完成矩陣的轉置
    # 先建立一個2x3的矩陣q
    
    q = np.array([[12,4,10],
                  [8,1,11]])
    
    print(f'q matrix is \n {q}.')
    print(f'\nq matrix 的形狀為 {np.shape(q)[0]} rows and {np.shape(q)[1]} columns , 可以表示為',np.shape(q)) #用np.shape()可以知道矩陣的欄列數量
    
    traspose_q = q.T
    
    print(f'\nq 的轉置矩陣為 \n {traspose_q}。')
    
    # more detials: https://numpy.org/doc/stable/reference/generated/numpy.ndarray.T.html

輸出結果:

    q matrix is 
     [[12  4 10]
     [ 8  1 11]].
    
    q matrix 的形狀為 2 rows and 3 columns , 可以表示為 (2, 3)
    
    q 的轉置矩陣為 
     [[12  8]
     [ 4  1]
     [10 11]]。

## 矩陣基本運算
### 矩陣可以相加、乘以常數、相乘或是內積。


### 在運算上，矩陣還可以有單位矩陣、反矩陣、對角畫矩陣與行列式，這些在高二下學期數學算得要死的東西，python幾行指令(甚至複製貼上)就有精準的答案了。
### 以下展示矩陣內積與相乘在python寫法上的差異:

    # 此cell我們只操作矩陣內積，想學矩陣相加請自己查資料
    # 一樣，我們定義矩陣q1,q2，再將其內積
    
    q1 = np.array([1,2,3])
    q2 = np.array([[1],
                  [2],
                  [3]])
    
    #對於1-D 矩陣(i =1 or j =1)來說，用以下函數算出的不是矩陣
    q1_dot_q2 = q1.dot(q2) # 1*1+2*2+3*3 = 14
    
    print(f'一維矩陣相乘(q1 dot q2) = {q1_dot_q2}.')
    print(f'q1 dot q2 的資料類型是 {type(q1_dot_q2)}.')       # 使用type()函數，他會告訴你輸入內容的資料類別(最前面講的那些，你們應該還沒忘記吧?)
    print(f'The value of q1 dot q2 = {q1_dot_q2[0]}.')       # 由於q1_dot_q2是一個np.array，且值儲存在第 1 row 第 1 colum中，我們可以透過q1_dot_q2[0]將其找到。
    print(f'q1_dot_q2[0] 的資料類型是 {type(q1_dot_q2[0])}.') # 由type()函數可知，q1_dot_q2[0]是一個整數(int)。

輸出的結果:

    一維矩陣相乘(q1 dot q2) = [14].
    q1 dot q2 的資料類型是 <class 'numpy.ndarray'>.
    The value of q1 dot q2 = 14.
    q1_dot_q2[0] 的資料類型是 <class 'numpy.int32'>.

### 在運算上，矩陣還可以有單位矩陣、反矩陣、對角畫矩陣與行列式，這些在高二下學期數學算得要死的東西，python幾行指令(甚至複製貼上)就有精準的答案了。
### 以下展示非1-D矩陣相乘:

    # 對於非1-D 矩陣，以下函數就會算出矩陣了
    q7 = np.array([[1,2,3],[4,5,6]])
    q8 = np.array([[1,2],
                   [4,5],
                   [6,7]])
    
    q7_x_q8 = np.dot(q7,q8) 
    
    print(f'非一維矩陣相乘為 \n{q7_x_q8}.')

輸出的結果:

    非一維矩陣相乘為 
    [[27 33]
     [60 75]].

### 以下展示單位矩陣與反矩陣運算:

    # 現在，我們來設定單位矩陣
    
    I2 = np.identity(2)
    
    print(f'二階方陣的單位矩陣為 \n{I2}')
    
    # 再來是反矩陣與行列式，我們設定新的矩陣q3
    
    q3 =np.array( [[1,2],
                   [3,2]])
    
    
    # 計算出行列式
    
    q3_det = np.linalg.det(q3)
    
    print(f'\nq3的行列式是 \n{q3_det}') # 使用np.linalg.det()將矩陣轉換成行列式
    
    # more details: https://numpy.org/doc/stable/reference/routines.linalg.html
    
    
    
    q3_inv = np.linalg.inv(q3) # 使用np.linalg.inv()將矩陣轉換成反矩陣
    
    print(f'\nq3的反矩陣是 \n{q3_inv}')
    
    # more details: https://numpy.org/doc/stable/reference/generated/numpy.linalg.inv.html

輸出的結果:

    二階方陣的單位矩陣為 
    [[1. 0.]
     [0. 1.]]
    
    q3的行列式是 
    -4.000000000000001
    
    q3的反矩陣是 
    [[-0.5   0.5 ]
     [ 0.75 -0.25]]

