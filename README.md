# 如何一步步用Google Colaboratory训练自己的模型？
# 11234006 賴仕泓 11210017鄭美雪
本文介绍如何利用Google Colaboratory免费GPU资源进行高效深度学习模型训练，并对比了GPU与CPU在训练过程中的性能差异。

使用Google Colaboratory必须翻墙
#為什麼要使用GPU?
搞深度学习就必须要使用GPU，否则训练太慢了，自己用CPU训练一个AlexNet网络，数据量大了内存不够，数据量小模型训练不够，训练时办公也还特别卡，搞了2天，结果训练准确率才到0.5，程序员吗，遇山开山遇水搭桥，于是想个办法突破自己电脑限制。
# 為什麼選擇Colab?
有以下几个原因：

第一、自己搞的是TensorFlow（Pytorch也可以用它，后期也准备削它）；

第二，最重要的免费使用GPU，提高训练模型的效率；

第三，不消耗自己电脑的pc，可以干其他事情。

第四，不用配置环境。

如果你也一样，也需要免费GPU来训练模型的话，那么一起用Colab。
# 登录Google云端硬盘
单击云端硬盘，用Google账号登录。界面如下：
<img width="1919" height="946" alt="螢幕擷取畫面 2025-11-01 035949" src="https://github.com/user-attachments/assets/4a5d5ab2-0209-469b-b682-7034041c3b56" />
单击左上角新建，得到如下的界面：
<img width="1909" height="943" alt="螢幕擷取畫面 2025-11-01 040001" src="https://github.com/user-attachments/assets/774d8ed7-03db-4b9e-a0c2-605e690476f8" />
你可以选择上传文件或者文件夹，你可以把训练模型的数据集和配置等上传上去，上传完之后，我们在点击更多\Google Colaboratory，进入下面页面：
<img width="1909" height="939" alt="螢幕擷取畫面 2025-11-01 040315" src="https://github.com/user-attachments/assets/75dce0b1-2158-429a-b354-0844ce515f81" />
单击红色框内按钮，装载Google云端硬盘，或者运行下面代码。

<img width="944" height="82" alt="螢幕擷取畫面 2025-11-01 045830" src="https://github.com/user-attachments/assets/6f1a9579-49fb-4ca6-aa26-bdf3114cb879" />


运行结果：
该代码只能在Google Colab环境中运行，在普通Python环境中无法执行，会提示模块不存在或环境不支持。

挂载成功后，我们可以在右侧种选择content/drive/MyDrive，找到云端硬盘，见下图:

<img width="1914" height="891" alt="螢幕擷取畫面 2025-11-01 040346" src="https://github.com/user-attachments/assets/0b2394be-5861-4602-b956-39c4e9e5882d" />

# 用GPU运行模型
Colab就是一个编辑器，其格式为.ipynb，只不过它支持了TensorFlow，Pytorch等深度学习框架，还提供了免费GPU，对于AI从业人员来说是福音，但是要使用TPU的话就需要Colab pro，需要付费。下面我开始构建模型和编译模型。

单击代码/新建代码单元格，开始写的自己模型。默认是CPU,若你想使用GPU，可以在代码执行程序/更改运行时类型/CPU进行设置。

下面用个简单是实例说明如何使用的：

<img width="478" height="678" alt="螢幕擷取畫面 2025-11-01 045645" src="https://github.com/user-attachments/assets/c4b76d7c-c544-44ba-932a-fb08c73f2456" />


采用CPU训练结果如下，每步需要90ms，一个迭代需要140s。

<img width="817" height="91" alt="螢幕擷取畫面 2025-11-01 041454" src="https://github.com/user-attachments/assets/7e3d45e1-f58a-4ce5-b592-a69ee59f22cc" />

接下来我们看看GPU模式下，每步耗时ms，每个迭代耗时7s，与CPU的140s相比，性能提升太多了。省下来的时间写个代码它不想吗？

<img width="614" height="675" alt="螢幕擷取畫面 2025-11-01 045244" src="https://github.com/user-attachments/assets/9b9a5499-7cb0-44ce-bcea-8b438a74cba7" />
