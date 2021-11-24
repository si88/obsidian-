Spyder
維基百科，自由的百科全書
跳至導覽跳至搜尋
Spyder
Spyder IDE
Spyder-windows-screenshot.png
Spyder在Windows上執行的螢幕截圖
開發者	Spyder開發團隊
穩定版本	
5.1.1（2021年8月4日，​40天前）
原始碼庫	
github.com/spyder-ide/spyder
編輯維基數據鏈結
程式語言	Python
作業系統	Windows, Linux, Mac OS
類型	整合式開發環境
授權條款	MIT授權條款
網站	github.com/spyder-ide
Spyder（前身為Pydee）是一個使用Python語言的開放原始碼跨平台科學運算整合開發環境(IDE)。Spyder整合了NumPy，SciPy，Matplotlib與IPython，以及其他開源軟體。[1][2]

與其他科學數值分析專用IDE（如Matlab或RStudio）相比，Spyder有下列特色：開放原始碼，以Python編寫並且可以相容於非自由軟體授權。Spyder可以使用附加元件擴充，內建互動式工具以處理數據。跨平台的特性使得它可以通過Anaconda，Winpython和Python（x,y）（Windows平台）。此外在主流的Linux發行版本例如Ubuntu、Debian、Fedora、OpenSUSE等等中都有它。

Spyder還可以通過繫結PyQt或PySide來使用Qt。


目錄
1	特性[3]
2	Light Mode
3	獨立性
3.1	獨立編譯
3.2	獨立執行
3.3	推薦模組
3.4	可選的模組
4	參見
5	參考文獻
6	外部連結
特性[3]
編輯器：支援多語言，具有函式和類檢視器，代碼分析特性（pyflakes和pylint獲得了支援），代碼補全，水平與垂直視窗的分離，直接跳入定義等等。
互動埠：Python或IPython埠都在工作區可以調整和使用。支援對編輯器里的代碼直接除錯。此外整合了Matplotlib的圖表顯示。
文件瀏覽器：在編輯器或埠中顯示任意類或函式呼叫的文件。
可變的瀏覽窗口：在檔案的執行過程中可以建立可變的瀏覽窗口。同時也可以對其進行編輯。
在檔案中尋找：支援正規表示式與Mercurial倉庫
其他擴展使用: Spyder也可以作為PyQt4/PySide的擴充使用（spyderlib模組）。例如，Spyder當中使用的Python互動端也可以被你用在自己的PyQt4/PySide程式中。
檔案瀏覽器
歷史記錄
Light Mode
Spyder也可以啟動Light mode來執行一個輕量化的IDE。Light mode是一個非常簡單輕巧的環境，僅包含了可變的瀏覽窗口和解釋埠。

Light mode已於Spyder 3.0.0版移除。[4]

獨立性
如果你是通過Python（x,y）、WinPython和Anaconda安裝的，那你就不需要去單獨去安裝下列組件。一般來說，這些組件都被上述的Python科學發行包囊括了。

獨立編譯
如果通過原始碼編譯安裝，唯一的要求就是Python的版本應當高於2.6。（注意，Python 3.2並不被支援）

獨立執行
你需要如下條件：

Python 2.6, 2.7, 3.3 or 3.4
PyQt4 4.6+, PySide 1.2.0+或PyQt5 5.2+（推薦使用PyQt4）
推薦模組
IPython 3.0+（一個增強型Python直譯器）
Rope v0.9.4+或Jedi 0.8 +（支援編輯器的代碼補全、呼叫提示以及轉到定義）
Pyflakes v0.5.0+（進行即時代碼分析）
Sphinx v0.6+（物件檢視器支援富文字模式）
Matplotlib v1.0+（2D/3D繪圖）
Pandas v0.13.1+（支援資料標籤與資料系列）
Numpy（N維陣列運算）
Scipy（訊號與圖像分析）
需要注意的一點是，在Ubuntu中使用IPython需要安裝ipython-qtconsole，而在Fedora中需要ipython-gui，在 Gentoo中需要安裝qt4 USE flag。

可選的模組
Pygments v1.6+（支援各種檔案類型的代碼突顯）
Pylint v0.25+（靜態代碼分析）
Pep8 v0.6+（代碼風格分析）
Psutil v0.3+（CPU和記憶體使用狀態條）