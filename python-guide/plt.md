# Matplotlib 套件繪圖(基本款)
### Matplotlib 是 Python 中最常用的繪圖函式庫。它可以讓我們將數據轉換成各種圖表，例如折線圖、散佈圖、長條圖等。

### 我們通常會匯入 matplotlib.pyplot 模組，並給它一個簡稱 plt。

    import matplotlib.pyplot as plt

## 繪製散佈圖與誤差棒 (Error Bar)
### 我們的任務是要將每組數據的平均值畫成散佈圖上的點，並用誤差棒來表示其不確定度(理組)或標準差(文組)。

### 我們可以用以下的此過程寫成以下的形式:

    import numpy as np
    import matplotlib.pyplot as plt
    
    # x 軸數據 (實驗中操縱變因的各個值)
    # 為了方便計算最適直線，我們假設 x 軸的值就是 1, 2, 3, 4, 5
    x_values = np.array([1, 2, 3, 4, 5])
    y_values = np.array(means)       # 平均值作為 y 軸
    y_errors = np.array(stds) # 不確定度作為 error bar 的大小
    
    # 開始繪圖
    plt.figure(figsize=(8, 6)) # 設定圖表大小 (可選)
    
    # 繪製散佈圖與 error bar
    # fmt='o' 表示用圓點標記數據點
    # capsize=5 讓 error bar 的頂端有短橫線，更美觀
    plt.errorbar(x_values, y_values, yerr=y_errors, fmt='o', capsize=5, label='mean')
    
    # 設定圖表標題與座標軸標籤
    # 由於plt不支援中文的座標軸標題，所以你們的座標軸標題、散佈圖主題與座標軸單位，都請用打英文
    plt.title('scatter plot')
    plt.xlabel('Independent variables')  # Independent variables : 操縱變因
    plt.ylabel('dependent variable')     # dependent variable : 應變變因
    
    # 顯示圖例
    plt.legend()
    
    
    # 顯示圖表
    plt.show()

### 執行此段程式碼後，會產生以下圖片:
![散步圖](./plot_error_bar.jpg)
