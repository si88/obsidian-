Qt
維基百科，自由的百科全書
跳至導覽跳至搜尋

本條目存在以下問題，請協助改善本條目或在討論頁針對議題發表看法。
此條目包含指南或教學內容。 (2018年12月1日)
請藉由移除或重寫指南段落來改善條目，或在討論頁提出討論。
此條目需要更新。 (2018年12月1日)
請更新本文以反映近況和新增內容。完成修改時，請移除本模板。
Qt
Qt logo 2016.svg
使用Qt Designer做GUI設計
使用Qt Designer做GUI設計
開發者	
Trolltech（1991年－2008年）
諾基亞（2008年－2011年）
Qt Project（2011年至今）
Digia（2012年－2014年）
The Qt Company（2014年至今）
穩定版本	
6.1.3[1]（2021年9月1日，​12天前）
預覽版本	
6.2.0 Beta3[2]（2021年8月19日，​25天前）
原始碼函式庫	
code.qt.io/cgit/qt/qtbase.git/
編輯維基數據鏈結
程式語言	C++
作業系統	跨平台
類型	應用程式框架
授權條款	LGPL、GPL、商業授權[3]
網站	www.qt.io
Qt（/ˈkjuːt/，發音同「cute」[4][5][6]）是一個跨平台的C++應用程式開發框架。廣泛用於開發GUI程式，這種情況下又被稱為部件工具箱。也可用於開發非GUI程式，比如控制台工具和伺服器。Qt被用於OPIE、Skype、VLC media player、Adobe Photoshop Elements、VirtualBox與Mathematica[7]以及被Autodesk [8][9]、歐洲太空總署[10]、夢工廠[11][12]、Google、HP[13]、KDE、盧卡斯影業[14]、西門子公司[15]、沃爾沃集團[16], 華特迪士尼動畫製作公司[17]、三星集團[18]、飛利浦[19]、Panasonic [20]所使用。

它是Digia公司的產品。Qt使用標準的C++和特殊的代碼生成擴充（稱為元物件編譯器（Meta Object Compiler, moc））以及一些巨集。通過語言綁定，其他的程式語言也可以使用Qt。

Qt是自由且開放原始碼的軟體，在GNU較寬鬆公共許可證（LGPL）條款下發布。所有版本都支援廣泛的編譯器，包括GCC的C++編譯器和Visual Studio。


目錄
1	歷史
2	支援平台
2.1	外部移植
3	授權模式
4	Qt模組
4.1	圖形使用者介面
4.2	訊號與槽
4.3	布局管理
4.4	Main Window
4.5	Graphics View
4.6	無障礙環境
4.7	國際化
4.8	多執行緒
4.9	語言綁定
4.10	Qt的hello world
4.11	編譯與執行
5	工具
6	Qt Solutions
7	使用
7.1	使用Qt的UI環境
7.2	視窗管理員
7.3	應用程式
8	參見
9	書目
10	參考文獻
11	外部連結
歷史
時間	Qt版本
1995年	Qt 1.0
1998年7月	Qt 1.4
1999年4月	Qt 1.4.4
1999年6月	Qt 2.0
2000年4月	Qt 2.1
2000年9月6日	Qt 2.2
2001年10月15日	Qt 3.0
2002年11月	Qt 3.1
2003年7月	Qt 3.2
2004年2月	Qt 3.3
2005年6月27日	Qt 4.0
2005年12月	Qt 4.1
2006年10月	Qt 4.2
2007年5月	Qt 4.3
2008年5月	Qt 4.4
2009年3月	Qt 4.5
2009年4月	Qt 4.5.1
2009年12月	Qt 4.6
2010年2月	Qt 4.6.2
2010年6月	Qt 4.6.3
2010年9月	Qt 4.7
2011年5月4日	Qt 4.7.3
2011年12月15日	Qt 4.8
2012年5月22日	Qt 4.8.2
2012年9月13日	Qt 4.8.3
2012年12月19日	Qt 5.0
2013年1月31日	Qt 5.0.1
2013年4月10日	Qt 5.0.2
2013年7月3日	Qt 5.1
2013年8月28日	Qt 5.1.1
2013年12月12日	Qt 5.2
2014年5月20日	Qt 5.3
2014年12月10日	Qt 5.4
2015年7月1日	Qt 5.5
2016年3月16日	Qt 5.6
2016年6月16日	Qt 5.7
2017年1月23日	Qt 5.8
2017年5月31日	Qt 5.9
2017年11月30日	Qt 5.10
2018年5月22日	Qt 5.11
2019年1月31日	Qt 5.12
2019年6月19日	Qt 5.13
2019年12月12日	Qt 5.14
2020年5月26日	Qt 5.15
Haavard Nord和Eirik Chambe-Eng於1991年開始開發「Qt」，1994年3月4日創立公司，最早名為Quasar Technologies，然後更名為Troll Tech，之後又再次更名為Trolltech，中文名是「奇趣科技」，2008年6月17日被NOKIA公司收購，以增強該公司在跨平台軟體研發方面的實力，更名Qt Software。

該工具包名為Qt是因為字母Q在Haavard的Emacs字體特別漂亮，而「t」代表「toolkit」，靈感來自Xt，X toolkit[21]。

2009年5月11日，諾基亞Qt Software宣布Qt原始碼管理系統面向公眾開放，Qt開發人員可通過為Qt以及與Qt相關的專案貢獻代碼、翻譯、範例以及其他內容，協助啟動和塑造Qt未來的發展。為了便於這些內容的管理，Qt Software啟用了基於Git和Gitorious開源專案的Web原始碼管理系統。

在推出開放式Qt代碼函式庫的同時，Qt Software在其網站釋出了其產品規劃（Roadmap）。其中概述了研發專案中的最新功能，展現了現階段對Qt未來發展方向的觀點，以期鼓勵社群提供回饋和貢獻代碼，共同啟動和塑造Qt的未來。2012年8月9日，Digia宣布已完成對諾基亞Qt業務及軟體技術的全面收購，並計劃將Qt應用到Android、iOS及Windows 8平台上。[22]

支援平台
使用Qt開發的軟體，相同的程式碼可以在任何支援的平台上編譯與執行，而不需要修改原始碼。會自動依平台的不同，表現平台特有的圖形介面風格。

Linux/X11：用於X Window System（如Solaris、AIX、HP-UX、Linux、BSD）。支援KDevelop和Eclipse IDE整合
Mac：用於Apple Mac OS X。基於Cocoa框架。支援Universal Binary。支援以Xcode編輯、編譯和測試。
Windows：用於Microsoft Windows。支援Visual Studio整合，也可以使用MinGW編譯
Embedded Linux：用於嵌入式Linux。可以透過編譯移除不常使用的組件與功能。透過自己的視窗系統QWS，不需依賴X Window System，直接寫入Linux影格緩衝。可以減少記憶體消耗。並提供虛擬影格緩衝QVFb，方便在桌面系統上進行嵌入式測試。
Windows CE / Mobile ：用於Windows CE
Symbian：用於Symbian platform
Maemo/MeeGo：用於Maemo
Wayland –用於Wayland顯示伺服器，Qt應用程式可以在運行時切換圖形後端，如X與Wayland。[23][24]
外部移植
自從諾基亞開放了Qt的原始碼給社群後，Gitorious上各種移植紛紛出現。下面是其中一部份：

Qt for OpenSolaris –用於OpenSolaris[25]
Qt for Haiku –用於Haiku OS[26]
Qt for OS/2 –仍然不完整的OS/2 eCS platform移植。[27]
Qt-iPhone –用於iPhone的實驗中產品。[28]
Android-Lighthouse –用於Android的實驗中產品。[29]
Qt for webOS –用於Palm Pre上webOS的實驗中產品。[30] [31]
Qt for Amazon Kindle DX –用於Amazon Kindle DX的實驗中產品。[32]
授權模式
Qt開放原始碼，並且提供自由軟體的使用者協定。使得它可以被廣泛地應用在各平台上的開放原始碼軟體開發中。

Qt提供三種授權方式。三種授權方式的功能、效能都沒有區別，僅在於授權協定的不同。LGPL和GPL是免費釋出，商業版則需收取授權費。[33]：

Qt商業版 - Qt商業授權適用於開發專屬和/或商業軟體。此版本適用於不希望與他人共享原始碼，或者遵循GNU較寬鬆公共許可證（LGPL）2.1版或GNU GPL 3.0版條款的開發人員。提供了技術支援服務。可以任意的修改Qt的原始碼，而不需要公開。
GNU LGPL v. 2.1- Qt 4.5.0及以後的版本開始遵循GNU LGPL。LGPL允許鏈結到它的軟體使用任意的授權條款，可以被專屬軟體作為類別館參照、釋出和銷售。可以購買支援服務。
GNU GPL v. 3.0 - 如果您希望將Qt應用程式與受GNU通用公眾授權條款（GPL）3.0版本條款限制的軟體一同使用，或者您希望Qt應用程式遵循該GNU授權條款版本的條款，則此版本Qt適用於開發此類Qt應用程式。可以購買支援服務。
Qt模組
經過多年發展，Qt不但擁有了完善的C++圖形函式庫，而且近年來的版本逐漸整合了資料庫、OpenGL函式庫、多媒體函式庫、網路、指令碼函式庫、XML函式庫、WebKit函式庫等等，其核心函式庫也加入了行程間通訊、多執行緒等模組，極大的豐富了Qt開發大規模複雜跨平台應用程式的能力，真正意義上實現了其研發宗旨「Code Less; Create More; Deploy Anywhere」。

由於各家編譯器規格不同，Qt本身為了跨平台相容性，只能以「最低相容規格」來設計。因此Qt必須具備RTTI、動態建立、Persistence/Serialization的基礎建設，以及建構出自己的容器元件。

下列模組提供一般的軟體開發
QtCore—QtCore模組是所有基於Qt的應用程式的基礎，提供訊號與槽的物件間通訊機制、IO、事件和物件處理、多執行緒
QtGui—包含了開發圖形使用者介面應用程式所需的功能。使用其支援的各個平台的原生圖形API。支援反鋸齒、向量形變。支援ARGB頂層widget
QtMultimedia—提供了用於多媒體內容處理的QML類型集和C++類集。同時提供存取攝像頭及音訊功能的API。包含的Qt音訊引擎支援三維音訊回放及管理。
QtNetwork—提供了網路程式設計功能。支援通用協定，如HTTP、FTP和DNS，包括對非同步HTTP 1.1的支援。與較低層的TCP/IP和UDP協定，如QTcpSocket、QTcpServer和QUdpSocket
QtOpenGL—提供在應用程式中使用OpenGL和OpenGL ES加入3D圖形。在Windows平台上亦支援Direct3D
QtOpenVG-提供OpenVG繪圖支援的一個外掛程式
QtScript—包含完全整合的ECMA標準指令碼引擎。提供訊號與槽機制簡化物件間通訊和QtScript偵錯程式。
QtScriptTools—額外的Qt Script組件
QtSql—將資料庫整合至應用程式。支援所有主要的資料庫驅動包括ODBC、MySQL、PSQL、SQLite、ibase、Oracle、Sybase、DB2。
QtSvg—支援SVG格式
QtWebKit—整合WebKit，提供了HTML瀏覽器引擎，便於在原生應用程式中嵌入網路內容和服務。
QtXml—提供了XML文件的閱讀器和編寫器、支援SAX和DOM。
QtXmlPatternsl—提供了XQuery和XPath引擎支援。
Phonon—整合Phonon，支援跨平台應用程式播放音訊和視訊內容。Qt5開始不支援Phonon。
Qt3Support—模組提供相容Qt 3.х.х版本的程式庫
QtDeclarative [34] - engine for declaratively building fluid user interfaces in QML
作業於Qt附帶工具的模組
QtDesigner—提供擴充Qt Designer的類別。
QtUiTools
QtHelp—協助整合線上檔案到應用程式中。
QtTest—提供單元測試框架和滑鼠和鍵盤類比功能。整合Visual Studio和KDevelop。
下列模組用於Unix開發
QtDBus
下列模組用於Windows開發
QAxContainer
QAxServer
圖形使用者介面
Qt的圖形使用者介面的基礎是QWidget。Qt中所有類型的GUI組件如按鈕、標籤、工具列等都衍生自QWidget，而QWidget本身則為QObject的子類別。Widget負責接收滑鼠，鍵盤和來自窗口系統的其他事件，並描繪了自身顯示在螢幕上。每一個GUI組件都是一個widget，widget還可以作為容器，在其內包含其他Widget。

QWidget不是一個抽象類別。並且可以被放置在一個已存在的使用者介面中;若是Widget沒有指定父Widget，當它顯示時就是一個獨立的視窗、或是一個頂層widget。QWidget顯示能力包含了透明化及Double-Buffering。Qt提供一種代管機制，當Widget於建立時指定父物件，就可把自己的生命週期交給上層物件管理，當上層物件被釋放時，自己也被釋放。確保物件不再使用時都會被刪除。

訊號與槽
Qt利用訊號與槽（signals/slots）機製取代傳統的callback來進行物件之間的溝通。當操作事件發生的時候，物件會發送出一個訊號（signal）；而槽（slot）則是一個函式接受特定訊號並且執行槽本身設定的動作。訊號與槽之間，則透過QObject的靜態方法connect來連結。

訊號在任何執行點上皆可發射，甚至可以在槽裡再發射另一個訊號，訊號與槽的連結不限定為一對一的連結，一個訊號可以連結到多個槽或多個訊號連結到同一個槽，甚至訊號也可連接到訊號。

以往的callback缺乏類型安全，在呼叫處理函式時，無法確定是傳遞正確型態的參數。但訊號和其接受的槽之間傳遞的資料型態必須要相符合，否則編譯器會提出警告。訊號和槽可接受任何數量、任何型態的參數，所以訊號與槽機制是完全類型安全。

訊號與槽機制也確保了低耦合性，發送訊號的類別並不知道是哪個槽會接受，也就是說一個訊號可以呼叫所有可用的槽。此機制會確保當在"連接"訊號和槽時，槽會接受訊號的參數並且正確執行。

布局管理
布局管理類別用於描述一個應用程式的使用者介面中的Widget是如何放置。當視窗縮放時，布局管理器會自動調整widget的大小、位置或是字型大小，確保他們相對的排列和使用者介面整體仍然保有可用性。

Qt內建的布局管理類型有：QHBoxLayout、QVBoxLayout、QGridLayout和QFormLayout。這些類別繼承自QLayout，但QLayout非繼承自QWidget而是直接源於QObject。他們負責widget的幾何管理。想要建立更複雜的版面組態，可以繼承QLayout來自訂版面組態管理員。

QHBoxLayout：組態widget成橫向一列
QVBoxLayout：組態widget成垂直一行
QGridLayout：組態widget在平面網格
QFormLayout：組態widget用於2欄標籤- field
Main Window
Qt提供了下列主視窗管理和相關的使用者介面組件的類別：

QMainWindow：提供一個標準的應用程式主視窗。當中可以包括選單、工具列、狀態列、停駐元件等元件。
QDockWidget：提供了一個可用於建立彈簧工具調色板或輔助窗口的widget。Dock widgets可以移、關閉、浮動為外部視窗。
QToolBar：提供了一個通用的工具欄widget，可以放入一些不同的action有關的工具，如按鈕、下拉選單、comboboxes和spin boxes。
Graphics View
Graphics View提供了用於管理和互動大量客製化的2D圖形物件的平面以及視覺化顯示物件的視圖widget，並支援縮放和旋轉功能。

整個Graphics View框架提供一個以Item為基礎的model-view設計。由3個主要的類別組成，分別是QGrphicsItem、QGraphicsScene和QGraphicsView。若干View可以顯示一個Scene，Scene中則包含不同幾何形狀的Item。

該框架包括一個事件傳播的架構，讓在Scene上的Item有雙精度的互動能力。Item可以處理鍵盤事件，鼠標按下、移動、釋放和雙擊事件，他們也可以跟蹤鼠標移動。

Graphics View使用BSP（二進位空間劃分）樹可非常快速地找到Item，因此即使是包含百萬個Item的大型Scene，也能即時圖形化顯示。

KDE中的Plasma亦是基於Graphics View實現的。

無障礙環境
無障礙環境需要無障礙相容的應用程式、輔助技術、以及輔助工具之間的合作。應用程式通常不會直接溝通輔助工具，而是通過一個輔助技術，這是一個應用程式和工具之間資訊交流的橋梁。使用者介面元素相關訊息，例如按鈕和滾動條，使用輔助技術來顯示。Qt支援Windows上的Microsoft Active Accessibility（MSAA）和Mac OS X上Mac OS X Accessibility。

無障礙相容的應用程式稱為AT-Servers，而輔助工具被稱為AT-Clients。Qt應用程式通常會是一個AT-Server，但特別的程式也可能如同AT-Client方式工作。

國際化
Qt的字體引擎能夠在同一時間正確的顯示各種不同的書寫系統。並且Qt內部使用Unicode編碼來儲存文字。

Qt的多國語言支援技術，可以讓應用程式中的文字全部使用英文撰寫，能夠在完全不需修改程式的狀況下，改變整個應用程式中的文字為另一個語系的文字，並能夠協助處理不同語言的單、複數問題。

獨立的翻譯檔案使得新增支援語言相當容易，同時翻譯檔案（.ts）為XML格式可以直接編輯或使用Qt Liguist進行翻譯，可讓無程式開發能力的翻譯者亦能獨自完成翻譯。Qt附帶的工具程式就能夠自動抽取需要翻譯的文字產生翻譯檔案。

多執行緒
Qt的執行緒支援是獨立於平台的執行緒類別，採用訊號與槽機制，實現類型安全的執行緒間通訊。這使得它易於開發具可移植性的多執行緒Qt應用程式。並能充分利用多核架構，獲得最佳執行效能，還能根據可用的處理器核心數自動調整使用的執行緒數。多執行緒程式設計也是一個執行耗時操作而不會凍結使用者介面的有效典範。

語言綁定
除了C++外，Qt還為其它多種電腦語言提供了應用程式介面，您也可以使用這些語言開發Qt應用程式。

Qt語言綁定
語言	名稱 - 綁定描述	QtCore	QtDesigner	QtGui	QtNetwork	QtOpenGL	QtSql	QtScript	QtSvg	QtTest	QtUiTools	QtWebKit	QtXml	開放原始碼軟體的授權	專有軟體的授權
Ada	QtAda	是	是	是	否[35]	是	是	否	否	否	是	否	是	GNU GPL	GMGPL + fee
C++	Qt – native C++	是	是	是	是	是	是	是	是	是	是	是	是	LGPL	LGPL or Proprietary + fee
C# & .NET	Qyoto – See also Kimono for KDE	是	是	是	是	是	是	是	是	是	是	是	是		
C# & .NET	qt4dotnet（頁面存檔備份，存於網際網路檔案館）													LGPL	LGPL
D語言	QtD（頁面存檔備份，存於網際網路檔案館）														
道語言	DaoQt（頁面存檔備份，存於網際網路檔案館）													LGPL	LGPL
Haskell	Qt Haskell														
Harbour	hbqt													GNU GPL	否
Java	Qt Jambi	是	是	是	是	是	是	是	是	是	是	是	是	LGPL	LGPL
Javascript（node.js）	node-qt（頁面存檔備份，存於網際網路檔案館）	僅有少數幾個類	否	僅有少數幾個類	否	否	否	否	否	僅有少數幾個類	否	否	否	BSD License	BSD License
Lisp	CommonQt（頁面存檔備份，存於網際網路檔案館） – Bindings for Common Lisp	是	是	是	是	是	是	是	是	是	是	是	是	BSD License	BSD License
Lua	lqt（頁面存檔備份，存於網際網路檔案館） - Bindings	是	否[36]	是	是	是	否	是	是	否	否	是	否	MIT	MIT
Lua	QtLua（頁面存檔備份，存於網際網路檔案館） - Bindings and script engine													LGPL	LGPL
Pascal	FreePascal Qt4（頁面存檔備份，存於網際網路檔案館）														
Perl	PerlQt4（頁面存檔備份，存於網際網路檔案館）	是	是	是	是	是	是	是	是	是	是	是	是	GNU GPL	否
PHP	PHP-Qt	是	是	是	是	是	是	是	是	是	是	是	是	LGPL	LGPL
Python	PyQt – has an associated text (ISBN 0132354187).	是	是	是	是	是	是	是	是	是	是	是	是	GNU GPL	專有 + fee
Python	PySide – from OpenBossa (a subsidiary of nokia).	是		是	是	是	是	是	是		是	是	是	LGPL	LGPL
Python	PythonQt（頁面存檔備份，存於網際網路檔案館）													LGPL	LGPL
R	qtbase（頁面存檔備份，存於網際網路檔案館）	是	是	是	是	是	是	是	是	是	是	是	是	GPL	否
Ruby	QtRuby	是	是	是	是	是	是	是	是	是	是	是	是	LGPL	LGPL
Tcl	qtcl（頁面存檔備份，存於網際網路檔案館）													GNU GPL	否
語言	名稱 - 綁定描述	QtCore	QtDesigner	QtGui	QtNetwork	QtOpenGL	QtSql	QtScript	QtSvg	QtTest	QtUiTools	QtWebKit	QtXml	開放原始碼軟體的授權	專有軟體的授權
Qt的hello world
將下面的代碼儲存到Hello.cpp中

#include <QtWidgets/QApplication>
#include <QtWidgets/QLabel>

int main(int argc, char *argv[])
{
    QApplication app(argc, argv);
    QLabel label("Hello, world!");
    label.show();
    return app.exec();
}
編譯與執行
新建一個檔案夾，命名為Hello
將程式碼Hello.cpp放入Hello檔案夾
在Hello檔案夾執行下列命令
qmake -project
qmake
make/gmake/nmake
這個取決於您的系統與編譯器設定
執行./release/Hello（在Windows中是release\Hello.exe）
工具
Qt提供了一些命令列和圖形工具，以方便和加速開發的過程。

Qt Creator：輕量級的Qt/C++ IDE開發環境。
qmake：跨平台構建工具，可簡化跨不同平台進行專案開發的構建過程。
Qt Designer：介面設計師。可以用拖拽的方式將Widget排放在介面上，支援版面組態，支援訊號與槽編輯。
Qt Assistant：Qt助手。Qt線上幫助檔案檢視工具。
Qt Liguist：翻譯工具。讀取翻譯檔案（如.ts、.po）並為翻譯人員提供友好的翻譯介面。
lupdate：從原始碼檔案或其他資源檔案中提取需要翻譯的字串，並將之存入xml格式的.ts檔案中。
lrelease：負責將.ts檔案轉化為程式使用的.qm檔案。.qm檔會去掉.ts檔中所有的空白和未翻譯的內容，並將儲存格式壓縮。
lconvert：用於翻譯檔案之間的格式轉換。
QVFb：虛擬影格快取裝置，類比framebuffer裝置（尺寸、色深），還可以透過skin類比硬體鍵盤的布局（包括特殊的按鍵），可以便捷在桌面系統機器上開發嵌入式程式
makeqpf：建立用於嵌入式裝置的qpf格式。qpf是一種預先彩現的字體，直接儲存成二進位內容，使用的時候可以用記憶體對映載入，從載入到繪製的過程不需要計算。
uic：User Interface Compiler。從使用者介面的檔案（.ui）生成C++代碼。
rcc：Resource Compiler。rcc工具根據.qrc檔案的內容將相關的資源在編譯過程中嵌入到Qt應用程式。
qtconfig：基於X11的Qt的組態工具和線上幫助。
qconfig：Qt Embedded（Linux和Windows CE）組態工具。
qtdemo：Qt的實例和示範項目的載入器。
qt3to4：協助移植Qt 3程式到Qt 4的工具。
qdbusxml2cpp：QtDBus XML compiler。將xml格式的D-Bus介面描述轉換成為C++原始碼
D-Bus Viewer：可以檢視D-Bus物件和資訊的工具。
Qt Visual Studio Add-in：Visual Studio整合
Qt Eclipse Integration：Eclipse整合
Qt Solutions
Qt Solutions提供Qt額外的組件和工具，使Qt的開發更有效率。在Qt 4.5之後，Qt Solutions加入了LGPL的授權

平台和特定行業的組件和工具
整合Qt與特定第三方產品的組件和工具
尖端的元件和新的工具也會被直接加入在Qt框架中發布
使用
使用Qt的UI環境
KDE Plasma Workspaces：著名的跨平台圖型環境。
MeeGo：基於Linux的開源手機作業系統
Motorola A760：UI以Qt/Embedded建構
OPIE
Qt Extended Improved
Razor-qt：桌面環境[37]
Symbian自第四版開始
視窗管理員
以下的視窗管理員，使用了Qt：

EggWM[38]
integrity
KWin
qlwm
deepin-wm
應用程式
一些出名的例子如下：

3DSlicer, a free open source software for visualization and medical image computing
AcetoneISO：映像檔掛載軟體
Adobe Photoshop Album, an image organizing application[39]
Arora：一款跨平台的開源網頁瀏覽器
Autodesk MotionBuilder, professional 3D character animation software
Autodesk Maya, 3D建模和動畫軟體
Avidemux, a Free Software program designed for multi-purpose video editing and processing
Avogadro：進階分子編輯器
BOUML，a free uml toolbox
chmcreator：開源的chm開發工具
CineFX：一款跨平台、開源、免費、影片剪輯，特效與合成套裝
CoCoA, a software for computations in commutative algebra
Dash Express, an Internet-enabled personal navigation device
DAZ Studio, a 3D figure illustration/animation application
Doxygen：API檔案產生器
EAGLE, tool for designing printed circuit boards (PCBs)
EiskaltDC++, a program that uses the Direct Connect protocol.
Emergent：神經網路模擬器。
FEKO, a software product for the simulation of electromagnetic fields
eva：Linux版QQ聊天軟體。
FreeCAD, a free and open source 3D-Solid and general purpose design CAD/CAE
FreeMat：一個自由開源的數值計算環境和程式語言
Full Tilt Poker, one of the most popular online poker programs
Gadu-Gadu：即時通訊軟體
Gambas, A free development environment based on a Basic interpreter
GoldenDict：一款開源的字典軟體
Google地球（Google Earth）：三維虛擬地圖軟體。
GNS：Cisco網路模擬器。
Guitar Pro 6, a tablature editor
刺蝟大作戰：一個基於百戰天蟲的開源遊戲。
Hydrogen, an advanced drum machine
ImageVis3D, a volume ray-casting application
Ipe：自由的向量圖形編輯器
ISE Webpack, a freeware EDA tool for Windows and Linux developed by Xilinx
Kadu, a Polish instant messenger using the Gadu-Gadu protocol
KDELibs：一個許多KDE程式都使用的共享庫，如Amarok、K3b、KDevelop、KOffice等。
KeePassX, a multi-platform port of KeePass, an open source password manager for Microsoft Windows
Last.fm播放器：著名的網際網路音樂社群網站的桌面使用者端。
Launchy：一個開放原始碼的快捷啟動器
LMMS：一個開放原始碼的音樂編輯軟體
LyX：使用Qt作為介面的LaTeX軟體。
Mathematica：Linux和Windows版本使用Qt作為GUI
Maxwell Render, a software package that aids in the production of photorealistic images from computer 3D model data
Mixxx：跨平台的開放原始碼DJ混音軟體
MuseScore，一個WYSIWYG的樂譜編輯器
MythTV：開源的數位視訊錄製軟體。
Nuke, a node-based compositor
PDFedit：自由的PDF編輯器
PokerTH, an open source Texas hold 'em simulator
Psi：一款XMPP網路協定的即時通訊軟體
qBittorrent：自由的BitTorrent P2P客戶端
QCad：一個用於二維設計及繪圖的CAD軟體
Qjackctl, a tool for controlling the JACK Audio Connection Kit
QSvn, a GUI Subversion client for Linux, UNIX, Mac OS X and Windows
Opera：著名的網頁瀏覽器。
Qt Creator, the free software cross-platform integrated development environment from Nokia
Qterm：跨平台的BBS軟體。
Quantum GIS：自由的桌面GIS
Quassel IRC：跨平台的IRC客戶端
QupZilla：跨平台的開放原始碼的Webkit網頁瀏覽器。
RealFlow, a fluid and dynamics simulator for the 3D industry
Recoll：桌面搜尋工具
Rosegarden, a free software digital audio workstation program
SciDAVis, a cross-platform plotting and data analysis program
Scribus：桌面排版軟體。
Skype：一個使用人數眾多的基於P2P的VOIP聊天軟體。
SMPlayer：跨平台多媒體播放器
Spotify, music streaming service.
Stellarium：一款天文學的自由軟體
TeamSpeak：跨平台的音效通訊軟體
Texmaker：一款跨平台的開放原始碼LaTeX編輯器
TeXworks, It is a graphical user interface to the typesetting system TeX.
Tlen.pl：波蘭人發明的即時通訊客戶端
TOra, a database administration tool[40]
UMPlayer:基於Mplayer的美觀多媒體播放器。
UniversalIndentGUI，an application which helps the user to beautify, reformat or indent various kinds of code.
Valknut, a program that uses the Direct Connect protocol
VirtualBox：虛擬機器軟體。
VisIt：一個開源型互動式並列可視化與圖形分析工具，用於檢視科學數據。
VisTrails, a scientific workflow management and visualization system
VLC多媒體播放器：一個體積小巧、功能強大的開源媒體播放器。
VoxOx, a unified communications software.
WordPress, based on Qt for Maemo and Symbian
wpa supplicant, a free software implementation of an IEEE 802.11i
Xconfig：Linux的Kernel組態工具
YY語音：又名「歪歪語音」，是一個可以進行線上多人語音聊天和語音會議的免費軟體。在中國大陸擁有龐大的使用者群。
咪咕音樂：咪咕音樂是中國移動傾力打造的正版音樂播放器[41]
WPS Office：金山公司（Kingsoft）出品的辦公軟體，與微軟Office相容性良好，個人版免費。