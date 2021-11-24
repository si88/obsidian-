Jupyter
維基百科，自由的百科全書
跳至導覽跳至搜尋
Project Jupyter
Jupyter logo.svg
簡稱	Jupyter
成立時間	2015
類型	非營利組織
目標	旨在透過所有程式語言完成資料科學的交換與計算[1]
服務地區
全球
官方語言
英文
網站	jupyter.org
Jupyter（聆聽i/ˈdʒuːpɪtər/）是一個非營利組織，旨在「為數十種程式語言的互動式計算開發開源軟體，開放標準和服務」。2014年由Fernando Pérez從IPython中衍生出來，Jupyter支援幾十種語言的執行環境。Jupyter Project的名稱是對Jupyter支援的三種核心程式語言的引用，這三種語言是Julia、Python和R，也是對伽利略記錄發現木星的衛星的筆記本的致敬。Jupyter專案開發並支援互動式計算產品Jupyter Notebook、JupyterHub和JupyterLab，這是Jupyter Notebook的下一代版本。


目錄
1	歷史
2	哲學
3	產品
3.1	Jupyter Notebook
3.2	Jupyter Kernels
3.3	JupyterHub
3.4	JupyterHub API
3.5	JupyterLab
4	行業應用
4.1	Colaboratory
5	媒體報導
6	資助和獎勵
7	Jupyter
7.1	Online
7.2	Windows
7.3	Mac
7.4	Linux
8	另請參閱
9	參考文獻
10	外部連結
歷史
2014年，Fernando Pérez宣布從IPython中衍生出一個名為Jupyter的專案。[2]IPython繼續以Python shell和Jupyter核心的形式存在，而IPython Notebook和其他與語言無關的部分移到了Jupyter名下。[3][4]Jupyter是語言無關的，它的名稱是對Jupyter支援的核心程式語言的引用，這些語言是Julia、Python和R，[5] 它支援幾十種語言 （頁面存檔備份，存於網際網路檔案館）的執行環境（也就是核心），這些語言包括Julia、R、Haskell、Ruby，當然還有Python（通過IPython核心）。[6]

2015年，GitHub和Jupyter專案宣布Jupyter Notebook檔案格式（.ipynb檔案）在GitHub平台上可以原生渲染。[7][8]

哲學
Jupyter專案的經營理念是通過開發開源軟體，支援所有程式語言之間的互動式資料科學和科學計算。根據Jupyter專案網站所言，「Jupyter將永遠是100%的開源軟體，所有人都可以免費使用，並在修改後的BSD授權的自由條款下發布。」[1]

產品
Jupyter Notebook
Jupyter Notebook（前身是IPython Notebook）是一個基於Web的互動式計算環境，用於創建Jupyter Notebook檔案。Notebook一詞可以通俗地引用許多不同的實體，主要是Jupyter Web應用程式、Jupyter Python Web伺服器或Jupyter檔案格式（取決於上下文）。Jupyter Notebook檔案是一個JSON檔案，遵循版本化模式，包含一個有序的輸入/輸出單元格列表，這些單元格可以包含程式碼、文本（使用Markdown語言）、數學、圖表和富媒體 (Rich media)，通常以「.ipynb」結尾附檔名。

Jupyter Notebook檔案可以通過Web界面中的「Download As」，通過nbconvert函式庫或shell中的「jupyter nbconvert」命令行界面，轉換為許多的開源標準輸出格式（HTML、演示投影片、LaTeX、PDF、reStructuredText、Markdown、Python)。

為了簡化Jupyter Notebook檔案在Web上的視覺化，nbconvert函式庫是通過nbviewer提供的一項服務，它可以獲取任何公開可用的Notebook檔案的URL，將其動態轉換為 HTML 並顯示給使用者。


IPython Notebook interface
Jupyter Notebook提供了一個基於瀏覽器的REPL，它建立在一些流行的開源函式庫之上:

IPython
ØMQ
Tornado（Web伺服器）
jQuery
Bootstrap（前端框架）
MathJax
Jupyter Notebook可以連接到許多核心（預設情況下，IPython核心附帶了Jupyter Notebook），從而允許使用多種語言進行編程。在2.3版本[9][10]（2014年10月）中，目前有49個與Jupyter相容的核心，可以用於許多程式語言，包括Python、R、Julia和Haskell。[11]

IPython在0.12版本（2011年12月）中添加了Notebook界面，2015年更名為Jupyter Notebook（IPython 4.0 - Jupyter 1.0）。[12]Jupyter Notebook類似於Maple、Mathematica和SageMath等程式的筆記本界面，SageMath是一種計算界面風格，起源於Mathematica在20世紀80年代。[13]據《大西洋》雜誌報導，在2018年初，使用者對Jupyter的興趣超過了Mathematica Notebook界面的流行程度。[13]

Jupyter Kernels
Jupyter Kernel是一個負責處理各種類型的請求（程式碼執行、程式碼補全、檢查）和提供回復的程式。核心通過網路使用ØMQ與Jupyter的其他組件通訊，因此可以在相同的或遠端的機器上。與許多其他類似於Notebook的接口不同，在Jupyter中，核心並不知道它們被附加到特定的檔案，並且可以同時從多個客戶端連接到它們。通常，核心是實現的，允許執行一種語言，但有幾個例外。

預設情況下，Jupyter附帶IPython作為預設核心，並通過ipykernel包裝器提供引用實現。許多語言都有各種品質和特性的核心。

JupyterHub
JupyterHub 是一個用於Jupyter Notebook的多使用者伺服器。它通過生成、管理和代理許多單一的Jupyter Notebook伺服器來支援許多使用者。

JupyterHub API
JupyterHub 向外暴露了以 REST 風格的 API 供開發者們使用，可參閱：[14]

它包攬了一系列對 Jupyter 的操作，諸如生成使用者環境，配置環境等。

JupyterLab
JupyterLab是Jupyter專案的下一代使用者界面。它在一個靈活且強大的使用者界面中提供了經典的Jupyter Notebook（筆記本、終端、文字編輯器、檔案瀏覽器、豐富輸出 (Rich Text) 等）所有熟悉的構建模組。第一個穩定版本於2018年2月20日發布。[15]

行業應用
Jupyter Notebook已經成為雲端計算的一個流行的使用者界面，主要的雲端提供商已經採用了Jupyter Notebook或其衍生工具作為雲端使用者的前端界面。例如亞馬遜的SageMaker Notebook[16]、Google的Colaboratory[17]以及微軟的Azure Notebooks[18]

Colaboratory
Colaboratory（也稱為Colab）是一個免費的Jupyter Notebook環境，它在雲端中運行，並將筆記本存儲在Google雲端端硬碟上。Colaboratory最初是Jupyter專案的一部分，[19]但最終被Google接管。[20]截止到2018年9月，Colaboratory只支援Python 2和Python 3核心，不支援其他Jupyter核心，比如Julia和R。

媒體報導
2016年2月11日，LIGO宣布首次觀測引力波。這次發布了原始的科學數據以及包含Python程式碼的Jupyter Notebook檔案，用於處理數據並從發現論文中複製數據。[21]
2018年4月5日，《大西洋》雜誌發表了一篇名為《科學論文過時了》的文章，討論了Jupyter Notebook和Mathematica Notebook在未來科學出版中的作用。[13]這篇文章引起了包括經濟學家保羅·羅默在內的著名科學家和學者的回應。[22]
資助和獎勵
2012年，Fernando Pérez因其在IPython（Jupyter專案的前身）上的工作而獲得自由軟體基金會的自由軟體進步獎。
2013年，IPython團隊獲得了艾爾弗·斯隆基金會115萬美元的資助，[23][24]該基金會資助了導致Jupyter專案誕生的早期工作。[25]
2015年，Jupyter專案被資助來自Leona M.和Harry B. Helmsley慈善信託基金，Gordon和Betty Moore基金會以及艾爾弗·斯隆基金會的聯合600萬美元，資助工作導致的擴展功能核心Jupyter工具，以及JupyterLab的創建。[26]
2018年5月2日，Jupyter專案指導委員會榮獲2017年ACM軟體系統獎，這是一個年度獎項，它表彰「對技術概念和商業接受度方面產生了持久影響的軟體系統」的個人或組織。[27]
Jupyter
Online
Binder[28]
Colaboratory[29]
Azure Notebooks[30]
Windows
Jupyter Portable[31]
Anaconda (Python發行版)
Mac
Anaconda (Python發行版)
Linux
Jupyter Lab[32]
Anaconda (Python發行版)
另請參閱
	自由軟體主題
GNU Octave
IPython
RStudio
SageMath
Scilab
Spyder
Wolfram Mathematica
參考文獻
 Project Jupyter - About Us. 2018-04-20 [2018-05-03]. （原始內容存檔於2020-12-01）.
 Project Jupyter // Speaker Deck. [2018-12-17]. （原始內容存檔於2020-11-12）.
 The Notebook, Qt console and a number of other pieces are now parts of Jupyter. [2018-12-17]. （原始內容存檔於2020-11-11）.
 The Big Split™.
 jupyter/design. GitHub. [2018-12-17]. （原始內容存檔於2020-11-11）.
 Project Jupyter | Home. [2018-12-17]. （原始內容存檔於2017-06-29）.
 sshirokov. GitHub + Jupyter Notebooks = <3. The GitHub Blog. 2015-05-07 [2018-04-10]. （原始內容存檔於2018-12-07） （美國英語）.
 Rendering Notebooks on GitHub – Jupyter Blog. Jupyter Blog. 2015-05-07 [2018-04-10].
 What's new in IPython > Issues closed in the 2.x development cycle. [2018-12-17]. （原始內容存檔於2020-10-21）.
 What's new in IPython > 2.0 Series. [2018-12-17]. （原始內容存檔於2020-02-21）.
 Jupyter kernels > List of (some) IPython compatible kernels. [2018-12-17]. （原始內容存檔於2021-02-04）.
 Notebook's announcement- 0.12 release note. [2018-12-17]. （原始內容存檔於2020-10-08）.
 Somers, James. The Scientific Paper Is Obsolete. The Atlantic. [2018-04-10]. （原始內容存檔於2019-11-09） （美國英語）.
 JupyterHub. jupyterhub.readthedocs.io. [2020-11-06].
 JupyterLab is Ready for Users – Jupyter Blog. Jupyter Blog. 2018-02-20 [2018-05-04]. （原始內容存檔於2019-06-04）.
 Amazon SageMaker on AWS. Amazon Web Services, Inc. [2018-05-09]. （原始內容存檔於2021-02-02） （美國英語）.
 Welcome to Colaboratory. research.google.com. [2018-05-09]. （原始內容存檔於2021-02-03）.
 Microsoft Azure Notebooks - Online Jupyter Notebooks. notebooks.azure.com. [2018-05-09]. （原始內容存檔於2020-11-29）.
 Nerds rejoice: Google just released its internal tool to collaborate on AI. Quartz. [2018-09-06]. （原始內容存檔於2020-12-02） （美國英語）.
 jupyter/colaboratory. GitHub. [2018-09-06]. （原始內容存檔於2019-02-16） （英語）.
 LIGO Open Science Center. losc.ligo.org. [2018-05-04]. （原始內容存檔於2016-02-15） （英語）.
 Jupyter, Mathematica, and the Future of the Research Paper – Paul Romer. paulromer.net. [2018-04-15]. （原始內容存檔於2020-11-05） （美國英語）.
 Sloan Foundation Grant — IPython. ipython.org. [2018-05-03]. （原始內容存檔於2020-11-14）.
 An Open Source Framework for Interactive, Collaborative and Reproducible Scientific Computing and EducationOpen Source Tools for Interactive, Collaborative and Reproducible Computing. ipython.org. [2018-05-03]. （原始內容存檔於2020-07-21）.
 Perez, Fernando. IPython 2015 Final Report - Sloan Foundation (PDF). ipython.org. December 28, 2015 [May 3, 2018]. （原始內容存檔 (PDF)於2020-10-07）.
 Helmsley Charitable Trust. helmsleytrust.org. [2018-05-03]. （原始內容存檔於2020-01-03） （英語）.
 Software System Award. ACM Awards. Association for Computing Machinery. [2016年4月28日]. （原始內容存檔於2016-05-05）.
 Binder. [2019-03-03]. （原始內容存檔於2021-02-03）.
 Colaboratory. [2019-03-03]. （原始內容存檔於2021-02-03）.
 Azure Notebooks. [2018-12-17]. （原始內容存檔於2020-11-29）.
 Jupyter Portable. [2019-03-03]. （原始內容存檔於2020-12-02）.
 Jupyter Lab. [2019-03-03]. （原始內容存檔於2020-12-09）.
外部連結
官方網站