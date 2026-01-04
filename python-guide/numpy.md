# Numpy 套件入門
### Numpy (Numerical Python) 是 Python 中用於科學計算的核心函式庫。它提供了高效能的多維陣列物件 (ndarray) 以及操作這些陣列的工具。

### 首先，我們需要「匯入」(import) Numpy 函式庫，通常會給它一個簡稱 np，方便之後使用。

    import numpy as np
    
    # 記得要執行喔

## Numpy 陣列 (Array)
### Numpy 陣列跟 Python 的串列(list)很像，但更適合用來做數值運算。

    # 從 Python 串列創建 Numpy 陣列
    data_array = np.array([1.0, 2.0, 3.0, 4.0, 5.0])
    print(data_array)
    
    # Numpy 陣列可以直接進行數學運算
    print(data_array * 2)  # 陣列中的每個元素都乘以 2
    print(data_array + 5)  # 陣列中的每個元素都加 5

輸出的結果:

[1. 2. 3. 4. 5.]

[ 2.  4.  6.  8. 10.]

[ 6.  7.  8.  9. 10.]

## 透過numpy array批量計算平均值與標準差
### 在實驗中，我們通常會對同一個物理量進行多次測量，以減少隨機誤差。
- 平均值 (Mean)：代表數據的集中趨勢。
- 標準差 (Standard Deviation)：代表測量數據的離散程度。

### 假設我們有五組數據，每組有三個測量值：
### 我們要分別計算每一組數據的平均值和標準差。Numpy 提供了方便的函式：
- np.mean(np_data_points)：計算平均值(必須輸入numpy陣列計算)
- np.std(np_data_points,ddof)：計算標準差，分成母體標準差(ddof = 0)和樣本標準差(ddof = 1)。由於我們的數據量少，因此皆採用樣本標準差。

### 現在，統整前面所學，會寫成下面的樣式:

    import numpy as np
    
    data_points = [
        [10.1, 10.3, 10.2],      # 第一個操縱變因下所量出的應變變因值
        [12.5, 12.3, 12.7],      # 第二個操縱變因下所量出的應變變因值
        [15.0, 15.1, 14.9],      # 以此類推
        [17.8, 17.5, 17.6],
        [20.2, 20.4, 20.3]
    ]
    
    means = []      # 用 list 來儲存每組數據的平均值
    stds = [] # 用 list 來儲存每組數據的標準差
    
    for group_data in data_points:
        # 將 Python 串列轉換成 Numpy 陣列，方便計算
        np_group_data = np.array(group_data)
    
        # 計算平均值
        mean_value = np.mean(group_data)
        means.append(mean_value)
    
        # 計算標準差
        std_value = np.std(np_group_data,ddof = 1)
    
        # 透過 append 將 std_value 加入 stds 這個list中
        stds.append(std_value)
    
    print("各組數據的平均值:", means)
    print("各組數據的標準差:", stds)


輸出的結果:

各組數據的平均值: [10.2, 12.5, 15.0, 17.633333333333333, 20.299999999999997]

各組數據的標準差: [0.10000000000000053, 0.1999999999999993, 0.09999999999999964, 0.1527525231651949, 0.09999999999999964]
