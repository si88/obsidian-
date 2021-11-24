# tf-idf[[編輯]

維基百科，自由的百科全書

[跳至導覽](https://zh.wikipedia.org/wiki/Tf-idf#mw-head)[跳至搜尋](https://zh.wikipedia.org/wiki/Tf-idf#searchInput)

**tf-idf**（英語：**t**erm **f**requency–**i**nverse **d**ocument **f**requency）是一種用於[資訊檢索](https://zh.wikipedia.org/wiki/%E8%B3%87%E8%A8%8A%E6%AA%A2%E7%B4%A2 "資訊檢索")與[文字挖掘](https://zh.wikipedia.org/wiki/%E6%96%87%E6%9C%AC%E6%8C%96%E6%8E%98 "文字挖掘")的常用加權技術。tf-idf是一種統計方法，用以評估一字詞對於一個檔案集或一個[語料庫](https://zh.wikipedia.org/wiki/%E8%AA%9E%E6%96%99%E5%BA%AB "語料庫")中的其中一份[檔案](https://zh.wikipedia.org/wiki/%E6%96%87%E4%BB%B6 "檔案")的重要程度。字詞的重要性隨著它在檔案中出現的次數成[正比](https://zh.wikipedia.org/wiki/%E6%AD%A3%E6%AF%94 "正比")增加，但同時會隨著它在語料庫中出現的頻率成反比下降。tf-idf加權的各種形式常被[搜尋引擎](https://zh.wikipedia.org/wiki/%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E "搜尋引擎")應用，作為檔案與使用者查詢之間相關程度的度量或評級。除了tf-idf以外，網際網路上的搜尋引擎還會使用基於連結分析的評級方法，以確定檔案在搜尋結果中出現的順序。

## 目次

-   [1原理](https://zh.wikipedia.org/wiki/Tf-idf#%E5%8E%9F%E7%90%86)
-   [2例子](https://zh.wikipedia.org/wiki/Tf-idf#%E4%BE%8B%E5%AD%90)
-   [3在向量空間模型裡的應用](https://zh.wikipedia.org/wiki/Tf-idf#%E5%9C%A8%E5%90%91%E9%87%8F%E7%A9%BA%E9%96%93%E6%A8%A1%E5%9E%8B%E8%A3%A1%E7%9A%84%E6%87%89%E7%94%A8)
-   [4tf-idf的理論依據及不足](https://zh.wikipedia.org/wiki/Tf-idf#tf-idf%E7%9A%84%E7%90%86%E8%AE%BA%E4%BE%9D%E6%8D%AE%E5%8F%8A%E4%B8%8D%E8%B6%B3)
-   [5參考資料](https://zh.wikipedia.org/wiki/Tf-idf#%E5%8F%83%E8%80%83%E8%B3%87%E6%96%99)
-   [6外部連結](https://zh.wikipedia.org/wiki/Tf-idf#%E5%A4%96%E9%83%A8%E9%80%A3%E7%B5%90)

## 原理[[編輯](https://zh.wikipedia.org/w/index.php?title=Tf-idf&action=edit&section=1 "編輯章節：原理")]

在一份給定的檔案裡，**詞頻**（term frequency，tf）指的是某一個給定的詞語在該檔案中出現的頻率。這個數字是對**詞數**（term count）的歸一化，以防止它偏向長的檔案。（同一個詞語在長檔案裡可能會比短檔案有更高的詞數，而不管該詞語重要與否。）對於在某一特定檔案裡的詞語{\displaystyle t_{i}}![t_{{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b61e3d4d909be4a19c9a554a301684232f59e5a)來說，它的重要性可表示為：

{\displaystyle \mathrm {tf_{i,j}} ={\frac {n_{i,j}}{\sum _{k}n_{k,j}}}}![{\mathrm  {tf_{{i,j}}}}={\frac  {n_{{i,j}}}{\sum _{k}n_{{k,j}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/05f25eceb713717766dd0b8ef4fd7d4a2f1a7a30)

以上式子中{\displaystyle n_{i,j}}![n_{{i,j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/292ee1f4999efc9a7938840c62ea763f9489ddd7)是該詞在檔案{\displaystyle d_{j}}![d_{{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3fa3426b07cfa37c76382ddbecfb4c880889657f)中的出現次數，而分母則是在檔案{\displaystyle d_{j}}![d_{{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3fa3426b07cfa37c76382ddbecfb4c880889657f)中所有字詞的出現次數之和。

**逆向檔案頻率**（inverse document frequency，idf）是一個詞語普遍重要性的度量。某一特定詞語的idf，可以由總檔案數目除以包含該詞語之檔案的數目，再將得到的商取以10為底的[對數](https://zh.wikipedia.org/wiki/%E5%B0%8D%E6%95%B8 "對數")得到：

{\displaystyle \mathrm {idf_{i}} =\lg {\frac {|D|}{|\{j:t_{i}\in d_{j}\}|}}}![{\displaystyle \mathrm {idf_{i}} =\lg {\frac {|D|}{|\{j:t_{i}\in d_{j}\}|}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a04206a294aef6302438c1f0281a32d55eb17755)

其中

-   |D|：語料庫中的檔案總數
-   {\displaystyle |\{j:t_{i}\in d_{j}\}|}![|\{j:t_{{i}}\in d_{{j}}\}|](https://wikimedia.org/api/rest_v1/media/math/render/svg/84bc20901276fa6a1c4c679205c5771d608553b2)：包含詞語{\displaystyle t_{i}}![t_{{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b61e3d4d909be4a19c9a554a301684232f59e5a)的檔案數目（即{\displaystyle n_{i,j}\neq 0}![n_{{i,j}}\neq 0](https://wikimedia.org/api/rest_v1/media/math/render/svg/466698d7cd0e5e8a1ed60f6570a45dd8686f5c64)的檔案數目）如果詞語不在資料中，就導致分母為零，因此一般情況下使用{\displaystyle 1+|\{j:t_{i}\in d_{j}\}|}![1+|\{j:t_{{i}}\in d_{{j}}\}|](https://wikimedia.org/api/rest_v1/media/math/render/svg/7686335bc9835f6f3c5fb6403e9857bc7f0aa7e7)

然後

{\displaystyle \mathrm {tf{}idf_{i,j}} =\mathrm {tf_{i,j}} \times \mathrm {idf_{i}} }![{\mathrm  {tf{}idf_{{i,j}}}}={\mathrm  {tf_{{i,j}}}}\times {\mathrm  {idf_{{i}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/252332a1e2cbaa57b804bb09e6a3690358e26927)

某一特定檔案內的高詞語頻率，以及該詞語在整個檔案集合中的低檔案頻率，可以產生出高權重的tf-idf。因此，tf-idf傾向於過濾掉常見的詞語，保留重要的詞語。

## 例子[[編輯](https://zh.wikipedia.org/w/index.php?title=Tf-idf&action=edit&section=2 "編輯章節：例子")]

有很多不同的[數學公式](https://zh.wikipedia.org/wiki/%E6%95%B0%E5%AD%A6%E5%85%AC%E5%BC%8F "數學公式")可以用來[計算](https://zh.wikipedia.org/wiki/%E8%A8%88%E7%AE%97 "計算")tf-idf。這邊的例子以上述的數學公式來計算。詞頻（tf）是一詞語出現的次數除以該檔案的總詞語數。假如一篇檔案的總詞語數是100個，而詞語「母牛」出現了3次，那麼「母牛」一詞在該檔案中的詞頻就是3/100=0.03。而計算檔案頻率（IDF）的方法是以檔案集的檔案總數，除以出現「母牛」一詞的檔案數。所以，如果「母牛」一詞在1,000份檔案出現過，而檔案總數是10,000,000份的話，其逆向檔案頻率就是lg（10,000,000 / 1,000）=4。最後的tf-idf的分數為0.03 * 4=0.12。

## 在向量空間模型裡的應用[[編輯](https://zh.wikipedia.org/w/index.php?title=Tf-idf&action=edit&section=3 "編輯章節：在向量空間模型裡的應用")]

tf-idf權重計算方法經常會和[餘弦相似性](https://zh.wikipedia.org/wiki/%E4%BD%99%E5%BC%A6%E7%9B%B8%E4%BC%BC%E6%80%A7 "餘弦相似性")（cosine similarity）一同使用於[向量空間模型](https://zh.wikipedia.org/wiki/%E5%90%91%E9%87%8F%E7%A9%BA%E9%96%93%E6%A8%A1%E5%9E%8B "向量空間模型")中，用以判斷兩份檔案之間的[相似性](https://zh.wikipedia.org/w/index.php?title=%E7%9B%B8%E4%BC%BC%E6%80%A7&action=edit&redlink=1 "相似性（頁面不存在）")。

## tf-idf的理論依據及不足[[編輯](https://zh.wikipedia.org/w/index.php?title=Tf-idf&action=edit&section=4 "編輯章節：tf-idf的理論依據及不足")]

tf-idf演算法是建立在這樣一個假設之上的：對區別文件最有意義的詞語應該是那些在文件中出現頻率高，而在整個文件集合的其他文件中出現頻率少的詞語，所以如果特徵空間坐標系取tf詞頻作為測度，就可以體現同類文字的特點。另外考慮到單詞區別不同類別的能力，tf-idf法認為一個單詞出現的文字頻數越小，它區別不同類別文字的能力就越大。因此引入了逆文字頻度idf的概念，以tf和idf的乘積作為特徵空間坐標系的取值測度，並用它完成對權值tf的調整，調整權值的目的在於突出重要單詞，抑制次要單詞。但是在本質上idf是一種試圖抑制雜訊的加權，並且單純地認為文字頻率小的單詞就越重要，文字頻率大的單詞就越無用，顯然這並不是完全正確的。idf的簡單結構並不能有效地反映單詞的重要程度和特徵詞的分布情況，使其無法很好地完成對權值調整的功能，所以tf-idf法的精度並不是很高。

此外，在tf-idf演算法中並沒有體現出單詞的位置資訊，對於Web文件而言，權重的計算方法應該體現出HTML的結構特徵。特徵詞在不同的標記符中對文章內容的反映程度不同，其權重的計算方法也應不同。因此應該對於處於網頁不同位置的特徵詞分別賦予不同的係數，然後乘以特徵詞的詞頻，以提高文字表示的效果。

## 參考資料[[編輯](https://zh.wikipedia.org/w/index.php?title=Tf-idf&action=edit&section=5 "編輯章節：參考資料")]

-   Salton, G. and McGill, M. J. 1983 _Introduction to modern information retrieval_. McGraw-Hill, [ISBN 0-07-054484-0](https://zh.wikipedia.org/wiki/Special:%E7%BD%91%E7%BB%9C%E4%B9%A6%E6%BA%90/0070544840).
-   Salton, G., Fox, E. A. and Wu, H. 1983 Extended Boolean information retrieval. _Commun. ACM_ 26, 1022–1036.
-   Salton, G. and Buckley, C. 1988 Term-weighting approaches in automatic text retrieval. _Information Processing & Management_ 24 (5): 513–523.