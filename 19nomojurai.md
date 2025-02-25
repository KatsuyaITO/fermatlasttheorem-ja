# 第19節:楕円曲線のモジュライ

***

## 第19節: 楕円曲線のモジュライ

モダンな数論幾何学における中心的な発見の一つは、**楕円曲線の族**を「レベル付け」と呼ばれる付加情報とともに整理し、それを**モジュライ空間**という幾何学的対象として扱う方法である。特に、$$X_0(N)$$（およびその変種）は「位数$$N$$の巡回部分群」などのレベル構造を伴う楕円曲線をパラメータ付ける**モジュラー曲線**として現れ、幾何学・数論・表現論が交錯する分野を形作る。これらの視点は最終的にフェルマーの最終定理の証明のような大きな成果へと結びついている。

本節では、以下の内容を概観する。

1. スキームを用いたモジュラー曲線 $$X_0(N)$$ の構成。
2. 整数モデルを考慮し、素数を法として還元した場合の振る舞い。
3. レベル構造（トーションに関するデータ）が幾何学的に何を意味するかの考察。

これらによって、各素数ごとの（局所的な）振る舞いを大域的なモジュライ理論へどのように組み込むかが明らかになり、ガロワ表現やモジュラー形式などの応用へと繋がっていく。

***

### 19.1 $$\displaystyle X_0(N)$$ の構成―モジュライ空間として

まず、**楕円曲線**および**モジュライ空間**という概念を、グロタンディークのファンクターポイントの観点で復習する。

#### 19.1.1 楕円曲線とそのファンクターポイント

**定義 19.1（楕円曲線）**

体 $$k$$ 上の**楕円曲線**とは、種数1の滑らかで射影的かつ幾何学的に連結な曲線 $$E$$ と、$$k$$-有理点 $$O \in E(k)$$ の組のことである。これは同時に、$$k$$ 上の1次元射影群スキームとみなすこともできる。

複素数体 $$\mathbb{C}$$ 上では、$$\mathbb{C}/\Lambda$$（$$\Lambda \subset \mathbb{C}$$ は格子）という形式で全ての楕円曲線が表され、区別点 $$O$$ は $$0 \in \mathbb{C}$$ の像に対応する。しかし数論的・代数幾何的な応用を念頭に置くと、$$\mathrm{Spec}(\mathbb{Z})$$ や有限体上など、一般の基底スキーム上で扱うことが重要となる。

**モジュライ問題とファンクターポイント**

モジュライ問題とは一般に、「ある種の幾何学的（あるいは代数的）対象を、追加構造も含めて、一つの幾何学的空間で総合的にパラメータ化できないか」という問いである。スキーム論の言葉では、あるモジュライ問題 $$\mathcal{M}$$ を

$$
\mathcal{M} : (\mathrm{Sch}/S)^{\mathrm{op}} \; \longrightarrow \; (\mathrm{Sets})
$$

という形の**関手**として定式化する（ここで $$S$$ は基底スキーム、典型的には $$\mathrm{Spec}(\mathbb{Z})$$ や $$\mathrm{Spec}(\mathbb{Q})$$ などで、$$\mathrm{Sch}/S$$ は $$S$$-スキームの圏を表す）。各 $$T \in \mathrm{Sch}/S$$ に対して、$$\mathcal{M}(T)$$ は $$T$$ 上の対象の族（および適当な同値関係）からなる集合となる。

本節の文脈では、「位数 $$N$$ の巡回部分群」を固定した楕円曲線をパラメータ化するモジュライ問題を考える。

1. $$T$$ 上の楕円曲線 $$E$$。
2. $$E$$ の $$N$$ 乗トーション部分群の中の**巡回部分群** $$C \subset E$$（位数 $$N$$）。

#### 19.1.2 粗モジュライ空間と $$X_0(N)$$

従来の（古典的な）モジュラー曲線は、複素解析的には「上半平面を特定の変換群で割った商空間」として定義されてきた。現代的には、これは**粗モジュライ空間**（coarse moduli space）であるとも理解される。

**定義 19.2（粗モジュライ空間）**

$$\mathcal{M}$$ を $$(\mathrm{Sch}/S)^{\mathrm{op}}$$ から $$(\mathrm{Sets})$$ への関手とする。スキーム $$X$$（$$S$$ 上）と自然変換

$$
\eta: \mathcal{M} \;\longrightarrow\; \mathrm{Hom}_{S}(-, X)
$$

の組が**粗モジュライ空間**と呼ばれるのは、以下の条件をみたすときである。

1. 任意の $$T$$ に対して、$$\eta$$ が誘導する写像 $$\mathcal{M}(T) \to \mathrm{Hom}_{S}(T,X)$$ は**集合論的**に全射である（すなわち、$$T \to X$$ という任意の射は何らかの族に対応する）。
2. $$Y$$ が他のいかなるスキームであっても、$$\mathcal{M} \to \mathrm{Hom}_{S}(-, Y)$$ という自然変換が与えられるなら、必ず一意的に $$X$$ を通って因数化する（つまり、可換図式を作るような $$X \to Y$$ が一意的に存在する）。

粗モジュライ空間は、対象たちの同型類をパラメータ化するが、必ずしもその空間上に「大域的な普遍族（universal family）」が存在するとは限らない。後述する\*\*細モジュライ空間（fine moduli space）\*\*は、普遍族を伴う場合に定義される。

**定理 19.3（粗モジュライ空間としての** $$X_0(N)$$ **の存在）**

$$\mathbb{Z}$$（したがって $$\mathbb{Q}$$）上に射影代数曲線 $$X_0(N)$$ が存在し、任意の体 $$k \supset \mathbb{Q}$$ に対して、$$X_0(N)(k)$$ の元は（同型を除いて）「$$k$$ 上の楕円曲線 $$E$$ とその巡回部分群 $$C\subset E$$（位数 $$N$$）」をパラメータ化する。

**（証明アイデアの概略）**

* 複素数上では、$$X_0(N)(\mathbb{C})$$ は古典的なモジュラー曲線 $$\Gamma_0(N)\backslash \mathcal{H}^*$$ （$$\mathcal{H}^*$$ は拡張上半平面）として得られ、これはモジュラー形式の理論により複素代数曲線でもある。
* デリーニュ＝ラポポールやカッツ＝メイザーによる一般基底上での楕円曲線のモジュライ理論を用いると、これらの解析的な記述がスキーム論においても一貫して貼り合わされ、**位数** $$N$$ **の巡回部分群を持つ楕円曲線**に対する粗モジュライ空間としてのスキーム $$X_0(N)$$ が構成できる。

このようにして、$$\mathcal{M}_{0}(N)$$（「$$T$$ 上の $$(E, C)$$」を対応させる関手）の粗モジュライ空間として $$X_0(N)$$ が得られる。

#### 19.1.3 細モジュライ空間：$$X(N)$$ と $$X_1(N)$$

$$X_0(N)$$ は粗モジュライ空間だが、モジュライ問題の**変種**によっては**細モジュライ空間**が得られ、そこでは普遍族が実際に存在する。これはレベル構造を微妙に調整することで、楕円曲線の自己同型が抑制される場合に起こる。

*   **フルレベル** $$N$$ **構造**:\
    $$T$$ 上の楕円曲線 $$E$$ に対し、

    $$
    E[N] \;\cong\; (\mathbb{Z}/N\mathbb{Z})^2_T
    $$

    という同型（ここで $$(\mathbb{Z}/N\mathbb{Z})^2_T$$ はランク $$N^2$$ の定数群スキーム）を与えることをレベル $$N$$ 構造という。これにより得られるモジュライ空間 $$X(N)$$ は、$$N \ge 3$$ の場合しばしば**細モジュライ空間**となる。これは楕円曲線の非自明な自己同型（ねじりを起こす $$\{\pm 1\}$$ など）が大きな $$N$$ では存在しにくくなるためである。
* **部分的なレベル構造**:
  * $$X_1(N)$$ は $$(E, P)$$（$$P$$ は $$E$$ 上の位数 $$N$$ の点）をパラメータ化する。
  * $$X_0(N)$$ は $$(E, C)$$（$$C\subset E$$ は位数 $$N$$ の巡回部分群）をパラメータ化する。

レベル構造が粗になるほど（$$X_0(N)$$ のように）自己同型が残存するため、細モジュライ空間にならなくなる。しかし、算術幾何の観点では、（スタックの言語を使うなどして）粗と細の差異は有限被覆 $$X(N) \to X_0(N)$$ を考えることでしばしば補完的に扱われる。

***

### 19.2 整数モデルと還元

モジュラー曲線をスキーム論の枠組みで構成する主目的の一つは、**整数的・局所的**性質（素数を法とする還元など）を解析するためである。これは基底を $$\mathbb{Q}$$ からその整数環 $$\mathbb{Z}$$（必要に応じて $$\mathbb{Z}[\tfrac{1}{N}]$$）へ拡張して考えることに対応する。

#### 19.2.1 ネロンモデルとモジュラー曲線の整数モデル

**定義 19.4（ネロンモデル）**

$$K$$ を数体または局所体とし、その整数環を $$\mathcal{O}_K$$ とする。$$E$$ を $$K$$ 上の楕円曲線とするとき、$$\mathcal{E}$$ を $$\mathcal{O}_K$$ 上の**ネロンモデル**というのは、以下を満たす滑らか・分離・有限型の群スキーム $$\mathcal{E}$$ を言う（その一般繊維は $$E$$ と同型）:

* どのような滑らか・分離スキーム $$\mathcal{Y}$$ とその一般点 $$\mathcal{Y}_\eta$$ 上の射 $$\mathcal{Y}_\eta \to E$$ についても、$$\mathcal{Y} \to \mathcal{E}$$ へ一意的に延長できる（普遍性）。

これは**良い還元**の概念を一般化する：楕円曲線 $$E$$ が素イデアル $$\mathfrak{p}$$ で良い還元を持つならば、$$\mathcal{E}_{\mathfrak{p}}$$ は $$\mathcal{O}_K/\mathfrak{p}$$ 上の楕円曲線となる。一方、悪い還元の場合でも、ネロンモデルの特異ファイバーを通じて構造を捉えられる。

$$X_0(N)$$ **の整数モデル**\
同様に、$$X_0(N)$$ も $$\mathrm{Spec}(\mathbb{Z})$$ 上で定義される曲線として考えることができ、これを**整数モデル** $$\mathcal{X}_0(N)$$ と呼ぶ。

* $$\mathcal{X}_0(N)$$ は $$\mathrm{Spec}(\mathbb{Z})$$ 上の（固有な）曲線で、その一般ファイバーは $$X_0(N)$$（$$\mathbb{Q}$$ 上）と一致する。
* 素数 $$p$$ を法としてこの曲線を還元すると、位数 $$N$$ のレベル構造を持つ楕円曲線が $$\mathbb{F}_p$$ 上でどのようにふるまうかが見えてくる。

この整数モデルは、**悪い還元**や**成分群**などを調べる上で核となる。モジュラー形式やガロワ表現の理論において、これらの局所的性質は非常に重要となる。

#### 19.2.2 普遍族における分岐

細モジュライ空間（例えば $$N \ge 3$$ における $$X(N)$$）が存在する場合、$$\mathcal{E} \to X(N)$$ という真の**普遍楕円曲線**が得られる。粗い場合でも、有効被覆やスタックの言語で「ほぼ」普遍族を扱うことができる。

* $$N$$ **を割る素数における分岐**: 幾何学的に見ると、位数 $$N$$ のトーション部分群を持つことは被覆写像 $$X(N) \to X_0(N)$$ における\*\*分岐（ramification）\*\*をもたらし得る。自己同型や退化（結節点を持つファイバーなど）が存在すると、対応するモジュライ空間上の点は被覆で分岐点となる。
* **カスプ（cusps）**: 整数モデル $$\mathcal{X}_0(N)$$ 上での「カスプ」は、退化した楕円曲線（例えばテート曲線によって解析的に表されるようなもの）に対応する。このカスプ点では普遍被覆や普遍族が非自明な分岐を起こし得る。

こうした局所的現象は、楕円曲線やモジュラー形式に付随する**ガロワ表現**を考察するとき極めて重要となる。素数 $$p$$ に対する局所ガロワ群の慣性群（イナーシャ群）がトーション点の被覆拡大にどのように作用するかが、分岐の仕方と直結するからである。

***

### 19.3 レベル構造の幾何学的意味

#### 19.3.1 モジュライ理論におけるトーション部分群

**なぜトーションのデータが重要か**\
体 $$k$$ 上の楕円曲線 $$E$$ における $$N$$-トーション部分群 $$E[N]$$ はスキーム論的にも「一般的には」$$(\mathbb{Z}/N\mathbb{Z})^2$$ と同型になる。レベル構造の付与とは、このトーション部分群の部分的あるいは完全な同定を与えることである。

1. $$X_0(N)$$: $$E[N]$$ 内の位数 $$N$$ の巡回部分群 $$C$$ 1つ。
2. $$X_1(N)$$: 位数 $$N$$ の点 $$P$$ 1つ。
3. $$X(N)$$: $$E[N]$$ と $$(\mathbb{Z}/N\mathbb{Z})^2$$ との全同型（シンプレクティック基底も含む）。

こうした違いにより、

* $$X_0(N)$$ のような粗いモジュライでは、同型を通じて別の巡回部分群に移りうる自己同型が残るため、細モジュライにはならない。
* $$X(N)$$ のように「フル」レベル構造を付けると、ほとんどの自己同型が排除され、普遍楕円曲線を伴う細モジュライ空間となる。

#### 19.3.2 モジュラー曲線のガロワ的解釈

この理論の白眉は、各種モジュラー曲線が互いに覆い合う構造を持ち、それが $$\mathrm{GL}_2(\hat{\mathbb{Z}})$$ や $$\mathrm{GL}_2(\mathbb{Z}/N\mathbb{Z})$$ の部分群を反映している点である。

* **被覆構造**: $$X(N) \to X_0(N)$$ は「フルレベル $$N$$ 構造から巡回部分群構造を忘れる」写像であり、有限被覆となる。多くの場合、適切に取り扱えばガロワ被覆にもなり、そのガロワ群は $$\mathrm{GL}_2(\mathbb{Z}/N\mathbb{Z})$$ の商群に同型となる。
* **局所-大域的ガロワ**: トーション点に対するガロワ作用を調べることで、素数 $$p$$ ごとの局所的挙動（慣性群など）と、モジュラー曲線の幾何学（素数 $$p$$ 上のファイバーでの分岐など）が結び付き、最終的には $$\mathbb{Q}$$ の絶対ガロワ群の表現として理解される。

**例 19.5（**$$X_0(4)$$ **の場合）**

複素数上では：

1. **解析的記述**: $$X_0(4)(\mathbb{C})$$ は上半平面を $$\Gamma_0(4)\subset \mathrm{SL}_2(\mathbb{Z})$$ で割った商空間に一致する。
2. **モジュライ解釈**: $$k$$ 上の点 $$X_0(4)(k)$$ は、位数4の巡回部分群 $$C\subset E$$ を持つ楕円曲線 $$(E, C)$$ を同型を除いて分類する。
3. $$X(4)$$ **による被覆**: より精密なモジュライ空間 $$X(4)$$ は、$$E[4]$$ に対して完全な $$\mathbb{Z}/4\mathbb{Z}$$-基底を与える構造をパラメータ化する。これを「忘れる」写像 $$X(4) \to X_0(4)$$ は有限被覆であり、そのガロワ群は $$\mathrm{GL}_2(\mathbb{Z}/4\mathbb{Z})$$ の部分群として理解される。自己同型やトーションの退化を許す曲線上の点において分岐が生じる。

***

### 19.4 歴史的・概念的補足

1. **解析から代数へ**: モジュラー曲線の初期研究は複素解析学（保型関数やフーリエ展開など）に基づいていたが、グロタンディーク以降のスキーム論・ファンクターポイントの手法によって、より普遍的・幾何学的な理解がもたらされた。
2. **類体論との関係**: 楕円曲線のトーション構造をコントロールすることは、数体のアーベル拡大を記述するヒルベルトの第12問題にも深く関わる。モジュラー曲線はガロワ群の作用を幾何学的に捉える方法を提供する。
3. **計算と応用**: $$X_0(N)$$ の具体例を計算すると、有理点や因子群などが分かり、これらは**Mordell–Weil定理**の解析や**Selmer 群**・**シャ群**・整数点の研究に役立つ。実際の計算法はフェルマー予想の議論や楕円曲線階層構造の証明などでも中心的役割を果たす。
4. **谷山–志村–ヴェイ理論への繋がり**: $$\mathbb{Q}$$ 上の楕円曲線が「モジュラー」になる（谷山–志村–ヴェイ予想、現在では定理）は、モジュライ空間および付随する $$\ell$$-進ガロワ表現の解析を通じて証明された。その帰結として、フェルマーの最終定理が（半安定楕円曲線のモジュラー性から）従うことは歴史的にも画期的であった。

***

### 参考文献

* **Deligne–Rapoport**: スキーム論によるモジュラー曲線の基礎的構成を扱った古典的論文。
* **Katz–Mazur,&#x20;**_**Arithmetic Moduli of Elliptic Curves**_: 楕円曲線の算術的モジュライ論、スタック、レベル構造について包括的に論じられている。
* **Silverman,&#x20;**_**Advanced Topics in the Arithmetic of Elliptic Curves**_: ネロンモデルの詳細やディオファントス幾何への応用が扱われている。
* **Shimura,&#x20;**_**Introduction to the Arithmetic Theory of Automorphic Functions**_: モジュラー曲線と保型関数を結びつける古典的見取り図。

以上で、レベル構造付き楕円曲線をパラメータ化するモジュラー曲線 $$X_0(N)$$ のスキーム論的構成、整数モデルや局所還元、トーション構造の幾何的意義を概観した。続く節では、楕円曲線の素イデアルでの還元やローカル・グローバルの整合性（トーション点やSelmer群など）をさらに詳しく調べ、ガロワ表現との関連を深めていく。これらの基礎はフェルマーの最終定理の証明を含む数論幾何の主要定理へと通じる道筋を照らしてくれる。
