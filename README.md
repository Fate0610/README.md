# 如何一步步用Google Colaboratory训练自己的模型？
# 11234006 賴仕泓 11210017鄭美雪
本文介紹如何利用Google Colaboratory免費GPU資源進行高效深度學習模型训练，並對比了GPU與CPU在訓練過程中的性能差異。

使用Google Colaboratory必須翻牆
#為什麼要使用GPU?
搞深度學習就必須要使用GPU，否則效率性價比都太低了 自己用CPU訓練一个AlexNet網路，結果跟GPU無法相比
# 為什麼選擇Colab?
有以下幾個原因：

第一、自己搞的是TensorFlow（Pytorch也可以用它，后期也準備削它）；

第二，最重要的免費使用GPU，提高訓練模型的效率；

第三，不消耗自己电脑的pc，可以做其他事情。

第四，不用配置環境。

如果你也一样，也需要免費GPU来訓練模型的话，那可以一起用Colab。
# 登入Google雲端硬碟
單擊雲端硬盤，用Google帳號登入，界面如下：
<img width="1919" height="946" alt="螢幕擷取畫面 2025-11-01 035949" src="https://github.com/user-attachments/assets/4a5d5ab2-0209-469b-b682-7034041c3b56" />
單擊左上角新建，得到如下的界面：
<img width="1909" height="943" alt="螢幕擷取畫面 2025-11-01 040001" src="https://github.com/user-attachments/assets/774d8ed7-03db-4b9e-a0c2-605e690476f8" />
你可以選擇上傳文件或者文件夾，你可以把訓練模型的數據集和配置等上傳上去，上傳完之后，可以點擊更多\Google Colaboratory，進入以下頁面：
<img width="1909" height="939" alt="螢幕擷取畫面 2025-11-01 040315" src="https://github.com/user-attachments/assets/75dce0b1-2158-429a-b354-0844ce515f81" />
單擊紅色框內按鈕，裝載Google雲端硬碟or運行以下代碼。

<img width="944" height="82" alt="螢幕擷取畫面 2025-11-01 045830" src="https://github.com/user-attachments/assets/6f1a9579-49fb-4ca6-aa26-bdf3114cb879" />


运行结果：
該代碼只能在Google Colab環境中運行，在普通Python環境中無法執行，會提示模塊不存在或環境不支持

掛載成功後，可以在右側選擇content/drive/MyDrive，找到雲端硬碟，如下圖：

<img width="1914" height="891" alt="螢幕擷取畫面 2025-11-01 040346" src="https://github.com/user-attachments/assets/0b2394be-5861-4602-b956-39c4e9e5882d" />

# 用GPU運行模型
Colab就是一個編輯器，其格式為.ipynb，只不過它支持了TensorFlow，Pytorch等深度學習框架，還提供了免費GPU，對於AI從業人員來說是福音，但是要使用TPU的話就需要Colab pro，需要付費。下面開始構建模型和編譯模型。

單擊代碼/新建代碼單元格，開始寫的自己模型。默認是是CPU,若想使用GPU，可以在代碼執行程序/更改運行時類型/CPU進行設定。

下面用個簡實例說明如何使用的：

<img width="478" height="678" alt="螢幕擷取畫面 2025-11-01 045645" src="https://github.com/user-attachments/assets/c4b76d7c-c544-44ba-932a-fb08c73f2456" />


CPU的訓練成果如下，可以看到每步需要至少90ms，一个迭代至少需要140s。

<img width="817" height="91" alt="螢幕擷取畫面 2025-11-01 041454" src="https://github.com/user-attachments/assets/7e3d45e1-f58a-4ce5-b592-a69ee59f22cc" />

在GPU模式下，每步耗時5ms，每个迭代耗時7s，在與CPU的140s對比下 GPU的性能提升太多了。

<img width="614" height="675" alt="螢幕擷取畫面 2025-11-01 045244" src="https://github.com/user-attachments/assets/9b9a5499-7cb0-44ce-bcea-8b438a74cba7" />
