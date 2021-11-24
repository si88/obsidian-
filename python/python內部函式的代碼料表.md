---
cards-deck: default
---

## abs(_x_)#card
返回一個數字的絕對值。參數可以是整數或浮點數。如果參數是一個複數，則返回它的模。
^1630760404172

## all(_iterable_)#card
如果 `iterable` 的所有元素均為 True（或 `iterable` 為空），則返回 `True`。相當於：

```
def all(iterable):
for element in iterable:
if not element:
return False
return True
```

## any(_iterable_)#card
如果 `iterable` 中有任何一個元素為 true，則返回 `True`。如果 `iterable` 為空，則返回 `False`。相當於：

```
def any(iterable):
for element in iterable:
if element:
return True
return False
```

## ascii(_object_)#card
類似 `repr()`，返回一個包含對象的可打印表示的字符串，但使用 `\x`，`\u` 或 `\U` 轉義符轉義由 `repr()` 返回的字符串中的非 ASCII 字符。這會生成一個類似於 Python 2 中 `repr()` 返回的字符串。

```
In [1]: s = 'python \n 中文'
In [2]: ascii(s)
Out[2]: "'python \\n \\u4e2d\\u6587'"
In [3]: repr(s)
Out[3]: "'python \\n 中文'"
```

## bin(_x_)#card
將整數轉換為以 “0b” 為前綴的二進制字符串。結果是一個有效的 Python 表達式。如果 `x` 不是Python `int` 對象，則必須定義返回整數的 `__index __()` 方法。一些例子：

```
>>> bin(3)
'0b11'
>>> bin(-10)
'-0b1010'
```

可以使用以下任意方式，控制是否需要前綴 “0b”：

```
>>> format(14, '#b'), format(14, 'b')
('0b1110', '1110')
>>> f'{14:#b}', f'{14:b}'
('0b1110', '1110')
```

有關更多信息，另請參閱 `format()`。
當 `x` 不是 `int` 類型時

```
In [1]: class Test:
...:     def __init__(self, n):
...:         self.n = n
...:
...:     def __index__(self):
...:         return self.n
...:
In [2]: t = Test(10)
In [3]: bin(t)
Out[3]: '0b1010'
```

## _class_ bool([_x_])#card
返回一個布爾值，即 `True` 或 `False` 中的一個。 x 使用標準[真值測試方式](https://docs.python.org/3.7/library/stdtypes.html#truth)進行轉換。如果 x 為 false 或省略，則返回 `False`; 否則返回 `True`。 bool 類是 `int` 的子類。它不能進一步子類化。它唯一的實例是 `False` 和 `True`。

## class bytearray([_source_[, _encoding_[, _errors_]]])#card
返回一個新的字節數組。 bytearray 類是一個在 `0 <= x < 256` 範圍內的可變整數序列。

可選的 `source` 參數可以用幾種不同的方式初始化數組：

-   如果它是一個字符串，則還必須給出 encoding（以及可選的 errors）參數; 然後 `bytearray()` 使用 `str.encode()` 將字符串轉換為字節。
-   如果它是一個整數，則將其作為數組的長度，並將用空字節進行初始化。
-   如果它是符合緩衝區接口的對象，則將使用該對象的只讀緩衝區來初始化字節數組。
-   如果它是一個 iterable，必須是 `0 <= x <256` 範圍內的可迭代對象，它們將被用作數組的初始內容。

沒有參數，就會創建一個大小為 0 的數組。

```
In [11]: bytearray(5)
Out[11]: bytearray(b'\x00\x00\x00\x00\x00')
In [12]: bytearray([23, 32, 4, 67, 9, 96, 123])
Out[12]: bytearray(b'\x17 \x04C\t`{')
In [13]: bytearray()
Out[13]: bytearray(b'')
```

## class bytes([_source_[, _encoding_[, _errors_]]])#card
返回一個新的 “bytes” 對象，它是一個在 `0 <= x <256` 範圍內的不可變整數序列。`bytes` 是 `bytearray` 的不可變版本 – 它具有相同的非變異方法和相同的索引和切片行為。

因此，構造函數參數解釋請參考 `bytearray()`。

字節對象也可以使用文字創建。請參閱[字符串和字節文字](https://docs.python.org/3.7/reference/lexical_analysis.html#strings)。

## callable(_object_)#card
如果 object 參數可調用，則返回 `True`，否則返回 `False`。如果返回 true，調用失敗仍然是可能的，但如果是 false，調用 object 將永遠不會成功。請注意，類是可調用的（調用一個類返回一個新的實例）; 如果類有一個 `__call __()`方法，則實例可以被調用。

3.2版本中的新功能：此功能在 Python 3.0 中首先被刪除，然後在 Python 3.2 中恢復。

```
In [19]: a = 1
In [20]: callable(a)
Out[20]: False
In [21]: def func():
...:     pass
...:
In [22]: callable(func)
Out[22]: True
In [23]: class A:
...:     pass
...:
In [24]: a = A()
In [25]: callable(a)
Out[25]: False
In [26]: class A:
...:     def __call__(self, *args, **kwargs):
...:         pass
...:
In [27]: a = A()
In [28]: callable(a)
Out[28]: True
```

## chr(_i_)#card
返回表示 Unicode 代碼點為整數 i 的字符的字符串。例如，`chr(97)` 返回字符串 `'a'`，而 `chr(8364)` 返回字符串 `'€'`。這是 `ord()` 的逆過程。

參數的有效範圍是從 0 到 1,114,111（基於 16 的 0x10FFFF）。如果超出這個範圍，將會拋出 ValueError。

## @classmethod#card
將方法轉換為類方法。
類方法將類作為第一個參數接收（隱式的），就像實例方法接收實例一樣。為了聲明一個類方法，習慣用法如下：
^1630760404218

```
class C:
@classmethod
def f(cls, arg1, arg2, ...): ...
```

!> 注意：類方法和靜態方法不是一個概念

## class complex([_real_[, _imag_]])#card
返回值為 real + imag*1j 的複數或者將字符串或數字轉換為複數。如果第一個參數是一個字符串，它將被解釋為一個複數，並且該函數必須在沒有第二個參數的情況下被調用。第二個參數不能是一個字符串。每個參數可以是任何數字類型（包括複數）。如果省略了 imag，它將默認為零，並且構造函數用作像 int 和 float 這樣的數字轉換。如果兩個參數均被省略，則返回 0j。
^1630760404245

!> 從字符串轉換時，該字符串不得在 `+` 或 `-` 運算符周圍包含空格。例如，`complex('1+2j')` 很好，但 `complex('1 + 2j')` 會引發 `ValueError`。

## delattr(object, name)#card
參數是一個對象和一個字符串。該字符串必須是對象屬性之一的名稱。該函數刪除指定的屬性（只要該對象允許）。例如， `delattr(x, 'foobar')` 等價於 `del x.foobar`。

## dict#card
class dict(`**kwarg`)  
class dict(`mapping`, `**kwarg`)  
class dict(`iterable`, `**kwarg`)
創建一個新的字典

```
In [38]: dict(name='jack',age=18)
Out[38]: {'name': 'jack', 'age': 18}
In [39]: dict({'name': 'jack'}, age=18)
Out[39]: {'name': 'jack', 'age': 18}
In [40]: dict([('name', 'jack'),('age', 18)])
Out[40]: {'name': 'jack', 'age': 18}
```

## dir([_object_])#card
嘗試返回 object 的有效屬性列表。如果沒有參數，則返回當前本地作用域中的名稱列表。
如果對象具有名為 `__dir__()` 的方法，則將調用此方法，並且必須返回屬性列表。這允許實現自定義 `__getattr__()`或 `__getattribute__()` 函數的對象自定義 `dir()` 報告其屬性。
默認的 `dir()` 機制對不同類型的對象有不同的表現，因為它試圖產生最相關的信息，而不是完整的信息：
-   如果對象是模塊對象，則列表包含模塊屬性的名稱。
-   如果對象是一個類型或類對象，則該列表包含其屬性的名稱，並遞歸地顯示其基礎的屬性。
-   否則，該列表包含對象的屬性名稱，其類屬性的名稱以及其類的基類的屬性的遞歸。

結果列表按字母順序排序。例如：

```
>>> import struct
>>> dir()   # show the names in the module namespace  
['__builtins__', '__name__', 'struct']
>>> dir(struct)   # show the names in the struct module 
['Struct', '__all__', '__builtins__', '__cached__', '__doc__', '__file__',
'__initializing__', '__loader__', '__name__', '__package__',
'_clearcache', 'calcsize', 'error', 'pack', 'pack_into',
'unpack', 'unpack_from']
>>> class Shape:
...     def __dir__(self):
...         return ['area', 'perimeter', 'location']
>>> s = Shape()
>>> dir(s)
['area', 'location', 'perimeter']
```

## divmod(_a_, _b_)#card
以兩個（非複數）數字作為參數，並在使用整數除法時返回由它們的商和餘數組成的一對數字。使用混合操作數類型時，適用二元算術運算符的規則。對於整數，結果與 `(a // b, a % b)` 相同。對於浮點數，結果是 `(q, a % b)`，其中 q 通常是 `math.floor(a / b)`，但可能小於 1。在任何情況下， `q * b + a % b` 都非常接近 a，如果 `a % b` 不為零，則它具有與 b 相同的符號，並且 `0 <= abs(a % b) < abs(b)`。

```
In [53]: divmod(10, 3)
Out[53]: (3, 1)
In [54]: divmod(10.1, 3)
Out[54]: (3.0, 1.0999999999999996)
```

## enumerate( _iterable_, _start=0_)#card
返回一個枚舉對象。 iterable 必須是一個序列，一個迭代器或其他支持迭代的對象。由 `enumerate()` 返回的迭代器的 `__next__()` 方法返回一個元組，該元組包含一個計數（從 start 開始，默認值為 0）以及遍歷迭代獲得的值。

```
>>> seasons = ['Spring', 'Summer', 'Fall', 'Winter']
>>> list(enumerate(seasons))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
>>> list(enumerate(seasons, start=1))
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
```

相當於：

```
def enumerate(sequence, start=0):
n = start
for elem in sequence:
yield n, elem
n += 1
```

## filter(_function, iterable_)#card
用那些 function 返回 true 的 iterable 元素構造一個迭代器。iterable 可以是序列，支持迭代的容器或迭代器。如果 function 為 `None`，則假定標識函數為 false，即為 false 的所有元素都被刪除。

!> 請注意，如果 function 不是 `None` ，`filter(function, iterable)` 等價於生成器表達式 `(item for item in iterable if function(item))` 。如果 function 是 `None`，等價於生成器表達式 `(item for item in iterable if item)` 。

```
In [8]: list(filter(None, [False, True, 0, 'test']))
Out[8]: [True, 'test']
```

## _class_ float([_x_])#card
返回一個由數字或字符串 x 構造的浮點數。
^1630760404273

在刪除前後空白字符後，輸入必須符合以下語法：

```
sign           ::=  "+" | "-"
^1630760404302
infinity       ::=  "Infinity" | "inf"
^1630760404330
nan            ::=  "nan"
^1630760404358
numeric_value  ::=  floatnumber | infinity | nan
^1630760404386
numeric_string ::=  [sign] numeric_value
^1630760404429
```

對於一般的 Python 對象 x，`float(x)` 委託給 `x .__float__()`。

如果沒有給出參數，則返回 0.0。

例子：

```
>>> float('+1.23')
1.23
>>> float('   -12345\n')
-12345.0
>>> float('1e-003')
0.001
>>> float('+1E6')
1000000.0
>>> float('-Infinity')
-inf
```

## format(_value_[, _format_spec_])#card
將值轉換為 “格式化” 表示，由 format_spec 控制。 format_spec 的解釋將取決於 value 參數的類型，不過，大多數內置類型都使用標準格式化語法：[格式化規範迷你語言](https://docs.python.org/3.7/library/string.html#formatspec)。
^1630760404456

默認 format_spec 是一個空字符串，通常與調用 str(value) 的效果相同。

對 `format(value, format_spec)` 的調用被轉換為 `type(value).__format__(value, format_spec)`，它在搜索 value 的 `__format__()` 方法時繞過實例字典。如果方法搜索到達 object 並且 format_spec 非空，或者 format_spec 或返回值不是字符串，則會引發 TypeError 異常。

在 version 3.4 中：如果 format_spec 不是空字符串，則 `object().__format__(format_spec)` 會引發 `TypeError`。

## class frozenset([_iterable_])#card
返回一個新的 frozenset 對象，可選地使用來自 iterable 的元素。 `frozenset` 是一個內置的類。

`frozenset` 是不可變的，存在哈希值，它可以作為字典的 key，也可以作為其它集合的元素。一旦創建便不能更改，沒有 add，remove 方法。

## getattr(_object_, _name_[, _default_])#card
返回 object 的指定屬性的值。name 必須是字符串。如果字符串是 object 屬性之一的名稱，則結果是該屬性的值。例如，`getattr(x, 'foobar')` 等同於 `x.foobar`。如果指定的屬性不存在，則返回默認值（如果提供），否則引發 `AttributeError`。

## globals()#card
返回表示當前全局符號表的字典。它總是當前模塊的字典（在函數或方法內部，它是定義它的模塊，而不是從中調用它的模塊）。
^1630760404486

## hasattr(_object_, _name_)#card
參數是一個對象和一個字符串。如果字符串是 object 屬性之一的名稱，則結果為 `True`，否則為 `False`。（這是通過調用 `getattr(object, name)` 並查看它是否引發 `AttributeError` 實現的。）

## hash(_object_)#card
返回對象的散列值（如果有）。哈希值是整數。它們用於在字典查找期間快速比較字典鍵。比較相等的數值具有相同的散列值（即使它們具有不同的類型，就像 1 和 1.0 一樣）。
^1630760404514

!> 對於具有自定義 `__hash__()` 方法的對象，請注意，`hash()` 會根據主機的位寬截斷返回值。

```
In [1]: class A:
...:     def __hash__(self):
...:         return 111111111111111111111111111111111111111
...:
In [2]: a = A()
In [3]: hash(a)
Out[3]: 1552656422630569496
In [4]: class A:
...:     def __hash__(self):
...:         return 11111111111
...:
...:
In [5]: a = A()
In [6]: hash(a)
Out[6]: 11111111111
```

## help([_object_])#card
調用內置的幫助系統。 （此功能用於交互式使用。）如果未提供參數，則交互式幫助系統將在解釋器控制檯上啟動。如果參數是一個字符串，那麼該字符串將被查找為模塊，函數，類，方法，關鍵字或文檔主題的名稱，並在控制檯上打印幫助頁面。如果參數是任何其他類型的對象，則會生成對象上的幫助頁面。
^1630760404549

## hex(_x_)#card
將整數轉換為以 “0x” 為前綴的小寫十六進制字符串。如果 x 不是 Python int 對象，則必須定義返回整數的 `__index __()` 方法。一些例子：

```
>>> hex(255)
'0xff'
>>> hex(-42)
'-0x2a'
```

如果要將整數轉換為帶有前綴或不帶前綴的大寫或小寫十六進制字符串，可以使用以下任一方式：

```
>>> '%#x' % 255, '%x' % 255, '%X' % 255
('0xff', 'ff', 'FF')
>>> format(255, '#x'), format(255, 'x'), format(255, 'X')
('0xff', 'ff', 'FF')
>>> f'{255:#x}', f'{255:x}', f'{255:X}'
('0xff', 'ff', 'FF')
```

!> 要獲取浮點數的十六進制字符串表示形式，請使用 `float.hex()` 方法。

## id(_object_)#card
返回一個對象的 “identity”。它是一個整數，它在其生命週期中保證對這個對象唯一且恆定。具有非重疊生命週期的兩個對象可能具有相同的 id() 值。
^1630760404587

CPython 實現細節：這是內存中對象的地址。

## input([_prompt_])#card
如果 prompt 參數存在，則將其寫入標準輸出而沒有尾隨換行符。然後該函數從輸入中讀取一行，將其轉換為一個字符串（剝離尾隨的換行符），然後返回該行。讀取 EOF 時，引發 EOFError。例：
^1630760404614

```
>>> s = input('--> ')  
--> Monty Python's Flying Circus
>>> s  
"Monty Python's Flying Circus"
```

## int#card
class int(x=0)  
class int(x, base=10)
返回一個由數字或字符串 x 構造的整數對象，如果沒有給出參數，則返回 0。如果 x 不是數字，則返回 `x.__int__()`。

```
In [22]: class A:
...:     def __int__(self):
...:         return 10
...:
In [23]: a = A()
In [24]: int(a)
Out[24]: 10
```

如果 x 不是數字或給定了 base，那麼 x 必須是一個 string， bytes 或 bytearray 實例，它表示以 base 為基數的整數文字。或者，文字可以在前面加上 `+`或 `-` （兩者之間沒有空格）。

```
In [25]: int('-10')
Out[25]: -10
In [26]: int('+10')
Out[26]: 10
In [27]: int('- 10')
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-27-a62cc7794a18> in <module>()
----> 1 int('- 10')
ValueError: invalid literal for int() with base 10: '- 10'
In [28]: int('1000',2)
Out[28]: 8
In [29]: int('ff',16)
Out[29]: 255
```

## isinstance(_object_, _classinfo_)#card
如果 object 參數是 classinfo 參數的實例或其（直接，間接或虛擬）子類的實例，則返回 true。如果 object 不是給定類型的對象，則該函數總是返回 false。如果 classinfo 是類型對象的元組， object 是其中任何一個類型的實例，則返回 true。如果 classinfo 不是類型或一組類型的元組，則會引發 `TypeError` 異常。

```
In [30]: isinstance(10, int)
Out[30]: True
In [31]: isinstance("str", (int, str))
Out[31]: True
In [32]: isinstance(max, int)
Out[32]: False
```

## issubclass(_class_, _classinfo_)#card
如果 class 是 classinfo 的子類（直接，間接或虛擬），則返回 true。一個類被認為是它自己的一個子類。 classinfo 可以是類對象的元組，在這種情況下，將檢查 classinfo 中的每個條目。在任何其他情況下，都會引發 `TypeError` 異常。

```
In [34]: issubclass(int, int)
Out[34]: True
In [35]: issubclass(10, int)
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-35-37910f193c07> in <module>()
----> 1 issubclass(10, int)
TypeError: issubclass() arg 1 must be a class
In [36]: issubclass(int, str)
Out[36]: False
```

## iter(_object_[, _sentinel_])#card
返回一個迭代器對象。根據第二個參數是否存在，第一個參數的解釋有所不同。如果沒有第二個參數，object 必須是支持迭代協議（`__iter__()` 方法）的集合對象，或者它必須支持序列協議（整數參數從 0 開始的 `__getitem__()` 方法）。如果它不支持這兩種協議，則會引發 `TypeError`。如果給出了第二個參數 sentinel，那麼 object 必須是可調用的對象。在這種情況下創建的迭代器將調用沒有參數的 object，以便對其 `__next__()` 方法進行調用；如果返回的值等於 sentinel，則會觸發`StopIteration`，否則將返回該值。

第二種形式的 `iter()` 的一個例子是按行讀取文件，直到到達某一行。以下示例讀取文件，直到 `readline()` 方法返回空字符串：

```
with open('mydata.txt') as fp:
for line in iter(fp.readline, ''):
process_line(line)
```

## len(s)#card
返回對象的長度（條目數量）。參數可以是一個序列（如 string，bytes，tuple，list 或 range）或集合（如字典，set 或 frozenset）。
^1630760404658

也可用於實現了 `__len__()` 方法的任意對象

```
In [40]: class A:
...:     def __len__(self):
...:         return 10
In [41]: a = A()
In [42]: len(a)
Out[42]: 10
```

## class list([_iterable_])#card
list 不是一個函數，它實際上是一個可變的序列類型。
^1630760404686

## locals()#card
更新並返回表示當前本地符號表的字典。在函數塊中調用時，locals() 返回自由變量，但不能在類塊中調用。
^1630760404716

!> 不應該修改其中的內容；更改可能不會影響解釋器使用的本地變量和自由變量的值。

## map(function, iterable, …)#card
返回一個將 function 應用於每個 iterable item 的迭代器，從而產生結果。如果傳遞額外的 iterable 參數，function 必須採用多個參數並應用於並行所有迭代中的項目。使用多個迭代器時，當最短迭代器耗盡時，迭代器停止。
^1630760404744

```
In [54]: list1 = [1, 2, 3, 4, 5, 6]
...: list2 = [4, 3, 7, 1, 9]
...:
In [55]: list(map(lambda x, y: x+y, list1, list2))
Out[55]: [5, 5, 10, 5, 14]
```

## max#card
`max(iterable, *[, key, default])`  
`max(arg1, arg2, *args[, key])`
返回 iterable 中的最大項或兩個或更多個參數中最大的項。

如果提供了一個位置參數，它應該是一個 iterable。iterable 中最大的 item 被返回。如果提供了兩個或多個位置參數，則返回最大的位置參數。

有兩個可選的關鍵字參數。 key 參數指定一個像 `list.sort()` 那樣的單參數排序函數。如果提供的迭代器為空，則 default 參數指定要返回的對象。如果迭代器為空且未提供缺省值，則會引發 `ValueError`。

如果最大值包含多個 item，則該函數返回遇到的第一個 item。這與 `sorted(iterable, key=keyfunc, reverse=True)[0]` 和 `heapq.nlargest(1, iterable, key=keyfunc)` 等其他排序工具穩定性保持一致。

```
In [60]: list1 = [4, 3, 7, 1, 9]
In [61]: max(list1, key=lambda x: -x)
Out[61]: 1
In [62]: max([])
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-62-a48d8f8c12de> in <module>()
----> 1 max([])
ValueError: max() arg is an empty sequence
In [63]: max([], default=1)
Out[63]: 1
```

## min#card
`min(iterable, *[, key, default])`  
`min(arg1, arg2, *args[, key])`
返回 iterable 中的最小項或兩個或更多個參數中的最小項。

如果提供了一個位置參數，它應該是一個 iterable。iterable 中的最小項被返回。如果提供兩個或多個位置參數，則返回最小的位置參數。

有兩個可選的關鍵字參數。 key 參數指定一個像 `list.sort()` 那樣的單參數排序函數。如果提供的迭代器為空，則 default 參數指定要返回的對象。如果迭代器為空且未提供缺省值，則會引發 `ValueError`。

如果最小值包含多個 item，則該函數返回遇到的第一個 item。這與 `sorted(iterable, key=keyfunc, reverse=True)[0]` 和 `heapq.nlargest(1, iterable, key=keyfunc)` 等其他排序工具穩定性保持一致。

## next(_iterator_[, _default_])#card
通過調用 `__next__()` 方法從 iterator 中檢索下一個 item。如果給出了 default，則在迭代器耗盡時返回它，否則引發 `StopIteration`。

## class object
返回一個新的無特徵的對象。object 是所有類的基類。它具有所有 Python 類實例通用的方法。這個函數不接受任何參數。

!> object 沒有 `__dict__`，所以不能為 object 類的實例指定任意屬性。

## oct(_x_)#card
將整數轉換為以 “0o” 為前綴的八進制字符串。結果是一個有效的 Python 表達式。如果 x 不是 Python int 對象，則必須定義返回整數的 `__index__()` 方法。例如：

```
>>> oct(8)
'0o10'
>>> oct(-56)
'-0o70'
```

如果要將整數轉換為八進制字符串，控制是否顯示前綴 “0o”，則可以使用以下任一方式。

```
>>> '%#o' % 10, '%o' % 10
('0o12', '12')
>>> format(10, '#o'), format(10, 'o')
('0o12', '12')
>>> f'{10:#o}', f'{10:o}'
('0o12', '12')
```

## open#card
`open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)`
打開 file 並返回相應的文件對象。如果文件無法打開，則會引發 `OSError`。

file 是一個類似路徑的對象，它提供要打開的文件的路徑名（絕對或相對於當前工作目錄）或要包裝的文件的整數文件描述符。 （如果給出文件描述符，則在返回的 I/O 對象關閉時關閉，除非 closefd 設置為 `False`。）

mode 是一個可選字符串，用於指定打開文件的模式。它默認為 `'r'`，表示使用文本的方式打開文件來讀取。其他常見的值是 `'w'` 用於寫入（如果文件已經存在，則覆蓋該文件），`'x'` 用於獨佔創建，`'a'` 用於附加（在某些 Unix 系統上，這意味著無論當前的搜索位置如何，所有寫操作都會附加到文件末尾）。在文本模式下，如果未指定編碼，則使用的編碼與平臺相關：調用 `locale.getpreferredencoding(False)` 以獲取當前語言環境編碼。（為了讀取和寫入原始字節，使用二進制模式並且不用指定編碼）可用的模式有：

字符

含義

`'r'`

用於讀取（默認）

`'w'`

用於寫入，首先覆蓋文件

`'x'`

用於獨佔創建，如果文件已經存在則失敗

`'a'`

用於寫入，追加到文件末尾（如果存在）

`'b'`

二進制模式

`'t'`

文本模式（默認）

`'+'`

打開磁盤文件進行更新（讀取和寫入）

`'U'`

通用換行符模式（已棄用）

默認模式是 `'r'`（用於讀取文本，`'rt'` 的同義詞）。對於二進制讀寫訪問，模式 `'w+b'` 打開並將文件刪減為 0 字節。 `'r+b'` 打開文件而不刪減。

如概述中所述，Python 區分二進制和文本 I/O。以二進制模式打開的文件（mode參數中包括 `'b'`）將內容作為字節對象返回，而不進行任何解碼。在文本模式下（默認情況下，或當 `'t'` 包含在 mode 參數中時），文件內容以 str 形式返回，字節首先使用平臺相關編碼進行解碼，或者使用指定的編碼（如果給出）。

!> Python 不依賴於底層操作系統的文本文件概念；所有的處理都由 Python 自己完成，因此是平臺無關的。

## ord(_c_)#card

給定一個代表一個Unicode字符的字符串，返回一個表示該字符的 Unicode code 點的整數。例如，`ord('a')` 返回整數 97，`ord('€')`（歐元符號）返回 8364。這是 `chr()` 的逆過程

## pow(_x_, _y_[, _z_])#card
返回 x 的 y 次方；返回 x 的 y 次方再除以 z 的餘數（計算效率比 `pow(x, y) % z` 更高）。雙參數形式 `pow(x, y)` 等價於使用冪運算符：`x**y`。

## print
`print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)`
將 objects 打印到文本流 file 中，以 sep 分隔，然後以 end 結尾。必須將 sep，end，file 和 flush（如果存在）作為關鍵字參數給出。

所有非關鍵字參數都會轉換為像 `str()` 那樣的字符串並寫入流中，由 sep 隔開，然後結束。sep 和 end 都必須是字符串；它們也可以是 None，這意味著使用默認值。如果沒有給出對象，`print()` 將只寫入 end。

文件參數必須是帶有 `write(string)` 方法的對象；如果它不存在或是 None，則將使用 `sys.stdout`。由於打印的參數會轉換為文本字符串，`print()` 不能用於二進制模式文件對象。對於這些，請改用 `file.write(...)`。

輸出是否緩衝通常由 file 決定，但如果 flush 關鍵字參數為 true，則強制刷新流。

## property#card
`class property(fget=None, fset=None, fdel=None, doc=None)`
返回一個 property 屬性。

fget 是獲取屬性值的函數。fset 是用於設置屬性值的函數。fdel 是刪除屬性值時會調用的函數。doc 為該屬性創建一個文檔字符串。

典型的用法是定義一個託管屬性 x：

```
class C:
def __init__(self):
self._x = None
def getx(self):
return self._x
def setx(self, value):
self._x = value
def delx(self):
del self._x
x = property(getx, setx, delx, "I'm the 'x' property.")
```

如果 c 是 C 的一個實例，`c.x` 將調用 getx，`c.x = value` 將調用 setx ，`del c.x` 將調用 delx。

如果給定，doc 將是 property 屬性的文檔字符串。否則，該屬性將複製 fget 的文檔字符串（如果存在）。這使得使用 `property()`作為裝飾器可以輕鬆創建只讀屬性：

```
class Parrot:
def __init__(self):
self._voltage = 100000
@property
def voltage(self):
"""Get the current voltage."""
return self._voltage
```

`@property` 修飾器將 `voltage()` 方法轉換為具有相同名稱的只讀屬性的 “getter”，並將 voltage 的文檔字符串設置為 `“Get the current voltage.”`。

property 對象具有可用作裝飾器的 getter，setter 和 deleter 方法，這些方法創建屬性的副本並將相應的存取器函數設置為裝飾函數。這可以用一個例子來解釋：

```
class C:
def __init__(self):
self._x = None
@property
def x(self):
"""I'm the 'x' property."""
return self._x
@x.setter
def x(self, value):
self._x = value
@x.deleter
def x(self):
del self._x
```

此代碼與第一個示例完全等效。請務必為附加函數提供與原始 property 相同的名稱（當前為 x）。

返回的 property 對象也具有與構造函數參數相對應的屬性 fget，fset 和 fdel。

## range#card
`range(stop)`  
`range(start, stop[, step])`
range 不是一個函數，它實際上是一個不可變的序列類型

```
In [8]: list(range(10))
Out[8]: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
In [9]: list(range(0, 10, 2))
Out[9]: [0, 2, 4, 6, 8]
```

## repr(_object_)#card
返回一個包含對象可打印表示的字符串。對於許多類型，此函數嘗試返回一個字符串，該字符串在傳遞給 `eval()` 時會產生一個具有相同值的對象，否則該表示是一個用尖括號括起來的字符串，其中包含對象類型的名稱以及其他信息包括對象的名稱和地址。一個類可以通過定義 `__repr__()` 方法來控制此函數為其實例返回的內容。

## reversed(_seq_)#card
返回一個反向迭代器。seq 必須是具有 `__reversed__()` 方法或支持序列協議（ `__len__()` 方法和整數參數從 0 開始的 `__getitem__()` 方法）的對象。

## round(_number_[, _ndigits_])#card
返回在小數點後舍入到精度 ndigits 的 number 。如果 ndigits 被省略或者是 `None`，它將返回最接近的整數表示。

對於支持 `round()` 的內建類型，值舍入到 10 的最接近的負 ndigits 次冪的倍數；如果離兩個倍數的距離相等，則舍入選擇偶數（因此，`round(0.5)` 和 `round(-0.5)` 都是 0，而 `round(1.5)` 是 2 ）。ndigits 可以是任何整數值（正數，零或負數）。如果使用一個參數調用則返回值是一個 integer，否則與 number 的類型相同。

```
In [10]: type(round(10.9))
Out[10]: int
In [11]: type(round(10.9, 2))
Out[11]: float
```

對於一般的 Python 對象 xxx，`round(xxx, ndigits)` 委託給 `xxx.__round__(ndigits)`。

!> `round()` 對於浮點數的行為可能會令人驚訝：例如，`round(2.675, 2)` 給出 2.67，而不是預期的 2.68。這不是一個 bug：這是由於大多數小數不能完全表示為浮點數的結果。

## class set([_iterable_])#card
返回一個新的集合對象，可選地使用來自 iterable 的元素。 set 是一個內置的類。
^1630760404775

## setattr(_object, name, value_)#card
它和 `getattr()` 是一對。參數是一個對象，一個字符串和一個任意值。該字符串可以是現有的屬性名或新的屬性名。如果該對象允許，該函數將 value 分配給該屬性。例如，`setattr(x, 'foobar', 123)` 等同於 `x.foobar = 123`。

## slice#card
`class slice(stop)`  
`class slice(start, stop[, step])`
返回表示由 `range(start, stop, step)` 指定的一組索引的切片對象。start 和 step 參數默認為 `None`。切片對象具有隻讀數據屬性 start、stop 和 step，它們只返回參數值（或它們的默認值）。他們沒有其他明確的功能；然而，它們被 Numerical Python 和其他第三方擴展使用。當使用擴展索引語法時，也會生成切片對象。例如：`a[start:stop:step]` 或 `a[start:stop, i]`。

```
In [5]: a = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
In [6]: s = slice(1, 8, 2)
In [7]: a[s]
Out[7]: [1, 3, 5, 7]
```

## sorted#card
`sorted(iterable, *, key=None, reverse=False)`
從 iterable 中的 item 中返回一個新的排序列表。
有兩個可選參數，必須將其指定為關鍵字參數。
key 指定一個帶有一個參數的函數，用於從每個列表元素中提取比較鍵：`key=str.lower`。默認值是 `None`（直接比較元素）。

reverse 是一個布爾值。如果設置為 `True`，那麼列表元素按照每個比較被顛倒的順序進行排序。

內置的 `sorted()` 函數排序是穩定的。如果確保不會更改比較相等的元素的相對順序，則排序是穩定的 。

## @staticmethod#card
將方法轉換為靜態方法。
靜態方法不會收到隱式的第一個參數。要聲明一個靜態方法，習慣用法如下：
^1630760404804

```
class C:
@staticmethod
def f(arg1, arg2, ...): ...
```

它可以在類（如 `C.f()`）或實例（如 `C().f()`）上調用。

Python 中的靜態方法類似於 Java 或 C++ 中的。

## str#card

`class str(object='')`  
`class str(object=b'', encoding='utf-8', errors='strict')`

返回一個字符串對象

## sum(_iterable_[, _start_])#card
從 start 開始，從左到右對 iterable 中的元素求和。 start 默認是 0，迭代的 item 通常是數字，並且不允許 start 的值為字符串。
對於有些情況，有比 `sum()` 更好的選擇， 比如：連接字符串應該用 `''.join(sequence)`。浮點數求和用 `math.fsum()` 。要連接一系列 iterable，請考慮使用 `itertools.chain()`。

## super([_type_[, _object-or-type_]])#card
返回一個代理對象，它委託方法給父類或者 type 的同級類。這對於訪問類中被覆蓋的繼承方法很有用。搜索順序與 `getattr()` 使用的順序相同，只不過 type 本身被跳過。

type 的 `__mro__` 屬性列出 `getattr()` 和 `super()` 使用的方法解析順序。該屬性是動態的，並且可以在繼承層次結構更新時更改。

如果省略第二個參數，則返回的 super 對象是未綁定的。如果第二個參數是一個對象，則 `isinstance(obj, type)` 必須為 true。如果第二個參數是類型，則 `issubclass(type2, type)` 必須為 true（這對類方法很有用）。

super 有兩種典型的使用情況。在具有單繼承的類層次結構中，可以使用 super 來引用父類，而不必明確命名它們，從而使代碼更易於維護。這種使用非常類似於在其他編程語言中 super 的使用。

第二種使用情況是在動態執行環境中支持協同多繼承。這種使用情況是 Python 獨有的，在靜態編譯語言或僅支持單繼承的語言中找不到。這使得可以實現 “菱形圖”，其中多個基類實現相同的方法。良好的設計指出此方法在每種情況下具有相同的調用順序（因為調用的順序在運行時確定，因為該順序適應類層次結構中的更改，並且因為該順序可以包括在運行時之前未知的兄弟類）。

對於這兩種用例，典型的超類調用如下所示：

```
class C(B):
def method(self, arg):
super().method(arg)    # This does the same thing as:
# super(C, self).method(arg)
```

!> 注意，`super()` 只實現顯式點分屬性查找的綁定過程，例如 `super().__getitem__(name)`。它通過實現自己的 `__getattribute__()` 方法來實現這一點，以便以支持協同多繼承需要的以可預測的順序搜索類。因此，`super()` 沒有定義隱式的查找語句或操作，例如 `super()[name]`。

!> 另請注意，除了零參數形式外，`super()` 不限於在方法內部使用。如果兩個參數的形式指定了準確的參數，就能進行正確的引用。零參數形式只能在類定義中使用，因為編譯器會填充必要的細節以正確檢索正在定義的類，以及訪問普通方法的當前實例。

## tuple([_iterable_])#card
tuple 不是一個函數，它實際上是一個不可變的序列類型
^1630760404833

## type#card
`class type(object)`  
`class type(name, bases, dict)`
有一個參數時，返回 object 的類型。返回值是一個類型對象，通常與 `object.__class__` 返回的對象相同。

建議使用 `isinstance()` 內置函數來測試對象的類型，因為它會考慮子類。

有三個參數時，返回一個新的類型對象。這實質上是類聲明的一種動態形式。name 字符串是類名，併成為 `__name__` 屬性；bases 元組逐項列出基類，併成為 `__bases__` 屬性；dict 是包含類體的定義的命名空間，並被複制到標準字典中以變為 `__dict__` 屬性。例如，以下兩條語句會創建相同的類型對象：

```
>>> class X:
...     a = 1
...
>>> X = type('X', (object,), dict(a=1))
```

## vars([_object_])#card
返回一個模塊、字典、類、實例或者其它任何一個具有 `__dict__` 屬性的對象的 `__dict__` 屬性。
模塊和實例這樣的對象的 `__dict__` 屬性可以更新；但是其它對象可能對它們的 `__dict__` 屬性的寫操作有限制（例如，類使用 `types.MappingProxyType` 來阻止對字典直接更新）。
如果不帶參數，`vars()` 的行為就像 `locals()`。注意，locals 字典只用於讀取，因為對 locals 字典的更新會被忽略。

## zip(*iterables)#card
製作一個迭代器，用於聚合來自每個迭代器的元素。
返回元組的迭代器，其中第 i 個元組包含來自每個參數序列或迭代的第 i 個元素。當最短的輸入迭代耗盡時，迭代器停止。使用單個迭代參數，它將返回 1 元組的迭代器。沒有參數，它返回一個空的迭代器。相當於：
^1630760404862

```
def zip(*iterables):
# zip('ABCD', 'xy') --> Ax By
sentinel = object()
iterators = [iter(it) for it in iterables]
while iterators:
result = []
for it in iterators:
elem = next(it, sentinel)
if elem is sentinel:
return
result.append(elem)
yield tuple(result)
```

只有當您不關心後續的，來自較長迭代器的未尾匹配值時，才應該用 `zip()` 。如果這些值很重要，請改用 `itertools.zip_longest()`。

與 `*` 操作符一起使用 `zip()` 可用於解壓縮列表：

```
>>> x = [1, 2, 3]
>>> y = [4, 5, 6]
>>> zipped = zip(x, y)
>>> list(zipped)
[(1, 4), (2, 5), (3, 6)]
>>> x2, y2 = zip(*zip(x, y))
>>> x == list(x2) and y == list(y2)
True
```
