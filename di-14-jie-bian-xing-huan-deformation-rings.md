# 第14節: 変形環（Deformation Rings）

有限体上のガロワ表現を、ゼロの標数をもつ完備局所環上の表現へ「持ち上げ」あるいは「変形」する方法を理解することは、現代数論における大きなブレイクスルーの一つでした。フェルマーの最終定理の証明においても、その核心的な役割を果たしています。基本的なアイデアは、$$\mathbf{Q}$$（あるいは任意の数体）の絶対ガロワ群のmod $$p$$表現を与えたとき、そこからより構造の豊かな環（たとえば$$p$$-進体の整数環やそのべき級数環）へ**すべて**の持ち上げを体系的に調べるというものです。

バリー・メイザー（Barry Mazur）の先見的な洞察は、これらの持ち上げ全体を**普遍変形環**（universal deformation ring）という一つの幾何（あるいは代数）オブジェクトにまとめ上げ、そのスペクトル（$$\mathrm{Spec}$$）を通じてすべての変形を（分岐制約や$$p$$での可換性条件、ordinarity などの追加条件付きで）媒介できるようにしたことです。本節では、メイザーの基礎的業績と、その後ワイルズ（Wiles）のフェルマーの最終定理証明に決定的役割を果たした発展を踏まえつつ、変形理論の主要概念を紹介します。

***

## 14.1 メイザーによる既約表現の変形枠組み

### 14.1.1 既約表現と普遍変形問題

#### 定義と設定

$$K$$ を数体とし、

$$
G_K \;=\; \mathrm{Gal}(\overline{K}/K)
$$

をその絶対ガロワ群とする。素数 $$p$$ を固定し、$$\mathbf{Q}_p$$ の有限拡大の整数環を $$\mathcal{O}$$ とする。ここで $$p$$**-進ガロワ表現** とは連続群準同型

$$
\rho \colon G_K \;\longrightarrow\; \mathrm{GL}_2(\mathcal{O})
$$

を指す。さらに、この表現を $$\mathcal{O}$$ の極大イデアル $$\mathfrak{m}_{\mathcal{O}}$$ で割り算する（すなわち、商環をとる）ことで得られる

$$
\overline{\rho} \colon G_K \;\longrightarrow\; \mathrm{GL}_2(\mathbf{F})
$$

を、**剰余表現（residual representation）** と呼ぶ。ここで $$\mathbf{F} = \mathcal{O}/\mathfrak{m}_{\mathcal{O}}$$ は $$p$$ を法とする有限体である。

実際の算術的応用では、しばしばこの $$\overline{\rho}$$ を出発点として、より大きな（あるいは性質の良い）環上へ「持ち上げる」ことを考えます。基本的な問いは以下のとおりです。

1. **どのような環へ** $$\overline{\rho}$$ **を持ち上げることができるか？**
2. **そうした持ち上げは（同型を除いて）いくつあるのか？**
3. **それらすべての持ち上げを一挙にパラメータ付けする、普遍的なオブジェクトを構成できるか？**

#### 変形を関手として捉える

これらの問いに体系的に答えるために、メイザーは関手的な方法を導入しました。具体的には：

* $$\mathbf{W}$$ を、剰余体が $$\mathbf{F}$$ となる完備離散付値環とする（$$\mathbf{F}$$ が完全体であれば、たとえばウィット環 $$W(\mathbf{F})$$ が典型例）。
* $$\mathcal{C}$$ を、**Artin 局所**$$\mathbf{W}$$**-代数** $$R$$ の圏とする。ここで $$R$$ の剰余体は $$\mathbf{F}$$（すなわち $$R/\mathfrak{m}_R \cong \mathbf{F}$$）となる。 $$\mathfrak{m}_R$$ は $$R$$ の唯一の極大イデアル。

$$\overline{\rho}$$ の **変形（deformation）** とは、ある $$R \in \mathcal{C}$$ 上で定義された連続表現

$$
\rho_R \colon G_K \;\longrightarrow\; \mathrm{GL}_2(R)
$$

であって、その剰余表現（$$\mathfrak{m}_R$$ による商）をとると $$\overline{\rho}$$ と同型になるものを指します。2つの変形 $$ho_R$$ と $$ho_R'$$ が **同値** であるとは、それらが $$\mathfrak{m}_R$$ による剰余で恒等写像となるような同型（同じ群表現の意味で）によって結ばれることを言います。

このとき得られる関手は

$$
\mathcal{D}_{\overline{\rho}} \colon \mathcal{C} \;\longrightarrow\; \mathbf{Sets},
\quad
\mathcal{D}_{\overline{\rho}}(R) \;=\; 
\{\,
\overline{\rho}\text{ の }R\text{上への変形の同値類}
\,\}
$$

となります。

#### メイザーの表現可能性定理

メイザーの変形理論における中心的な定理は次のものです。

> **（定理：メイザーの表現可能性定理）**\
> \*$$\overline{\rho}$$ が十分「良い」（例えば絶対既約である、あるいは $$\mathbf{F}$$ 上での自己準同型が定数倍しかない）と仮定する。このとき、関手 $$\mathcal{D}_{\overline{\rho}}$$ は**可換局所環** $$R_{\overline{\rho}}^{\mathrm{univ}}$$ によって表現される。すなわち、次を満たす**普遍変形**
>
> $$
> \rho^{\mathrm{univ}} \colon G_K \;\longrightarrow\; \mathrm{GL}_2(R_{\overline{\rho}}^{\mathrm{univ}})
> $$
>
> が存在する。これは「普遍」という意味で、もし任意の $$R \in \mathcal{C}$$ 上の変形 $$ho_R$$ が与えられれば、ただ一つの $$\mathbf{W}$$-代数準同型\
> $$\varphi \colon R_{\overline{\rho}}^{\mathrm{univ}} \to R$$ によって $$ho^{\mathrm{univ}}$$ から「因数分解」する形で得られる。さらに、$$\mathcal{D}_{\overline{\rho}}(R)$$ は $$\mathrm{Hom}_{\mathcal{C}}(R_{\overline{\rho}}^{\mathrm{univ}}, R)$$ と自然に同型になる。\*

この環 $$R_{\overline{\rho}}^{\mathrm{univ}}$$ を **普遍変形環**（universal deformation ring）と呼び、$$\rho^{\mathrm{univ}}$$ を $$\overline{\rho}$$ の **普遍変形**（universal deformation）と呼びます。

***

### 14.1.2 変形理論の動機

普遍変形環は、元の mod $$p$$ 表現 $$\overline{\rho}$$ のさまざまな持ち上げ（しばしば異なる算術的性質をもつ）を、1つの幾何学的（あるいは代数的）対象として「点」によって整理します。その主な応用としては次のようなものがあります。

1. **持ち上げの総括的パラメータ付け:** 普遍変形環の極大イデアル（や素イデアル）を考えることで、特定の性質を持つ持ち上げを具体的に得ることができる。
2. **局所条件の付加:** しばしば各素点（素イデアル）において、既約表現に対し何らかの局所的なふるまい（分岐条件や$$p$$でのordinarityなど）を課したい場合がある。そうした局所条件を課すと、普遍変形環の商環によって、その条件を満たす変形だけを表すことができる。
3. **幾何学的・算術的比較:** _すべ&#x3066;_&#x306E;持ち上げが $$\mathrm{Spec}\bigl(R_{\overline{\rho}}^{\mathrm{univ}}\bigr)$$ の内部に含まれるため、異なる持ち上げを体系的に比較することが可能になる。これはガロワ表現と保型形式の比較に用いられる「既約表現のモジュラーリフティング定理（modularity lifting theorems）」で鍵となる。

歴史的に、メイザーの理論は最初、円分拡大や岩澤理論（Iwasawa theory）の研究から動機付けられ、その後、ワイルズらによってガロワ表現とHecke代数を結びつける形へと洗練され、フェルマーの最終定理の証明のエンジンとなりました。

***

## 14.2 構成とコホモロジー的手法

### 14.2.1 $$R_{\overline{\rho}}^{\mathrm{univ}}$$ の構成概略

表現可能性の証明には変形理論におけるシュレッシンガー（Schlessinger）の基準を用いるのが一般的ですが、直観的な概要は次のように説明できます。

1. **「大きな」環から始める:** 変数がたくさんある冪級数環 $$\mathbf{W}[[x_1, \ldots, x_n]]$$ を考える。ここでの $$\mathrm{GL}_2\bigl(\mathbf{W}[[x_1,\ldots,x_n]]\bigr)$$ は「汎用的な」2次元表現の行列係数を担うには十分大きい。
2. **ガロワ的関係を課す:** 各元 $$g \in G_K$$ の像が、この大きな行列環上で、ガロワ群がもつ関係式（連続性や余剰コホモロジー条件など）を満たし、かつ極大イデアルで割り算したときに $$\overline{\rho}(g)$$ を再現するようにする。
3.  **商環を得る:** それらの関係式で生成されるイデアル $$I$$ を導入して

    $$
    R_{\overline{\rho}}^{\mathrm{univ}} \;\coloneqq\; \mathbf{W}[[x_1,\dots,x_n]] / I
    $$

    と定義する。これが、**普遍性**（universal property）を満たすように構成される。

正式には、この構成をシュレッシンガーの基準などを使って厳密に示します。変形関手 $$\mathcal{D}_{\overline{\rho}}$$ の性質や、Artin 局所環の逆極限（projective limit）としての構造を利用することで証明が行われます。

***

### 14.2.2 接空間と障害理論（Obstructions）

普遍変形環 $$R_{\overline{\rho}}^{\mathrm{univ}}$$ の「大きさ」（次元など）を調べる上で強力な道具となるのが、**ガロワコホモロジー** と呼ばれる理論、特に1次・2次コホモロジー群です。

*   **接空間（tangent space）** $$\mathfrak{m}_{\mathrm{univ}} / \mathfrak{m}_{\mathrm{univ}}^2$$（$$R_{\overline{\rho}}^{\mathrm{univ}}$$ の極大イデアル $$\mathfrak{m}_{\mathrm{univ}}$$ に対する接空間）は、

    $$
    H^1\bigl(G_K,\mathrm{ad}(\overline{\rho})\bigr)
    $$

    と同型になります。ここで $$\mathrm{ad}(\overline{\rho})$$ は付随表現（adjoint representation）と呼ばれるもので、$$\mathbf{F}$$ 上の $$2\times2$$ 行列全体に共役作用（随伴作用）をする4次元表現です。
*   **障害（obstruction）** は、

    $$
    H^2\bigl(G_K,\mathrm{ad}(\overline{\rho})\bigr)
    $$

    によって制御されます。もしこの群が大きいと、一段階先の変形へ拡張できない（すなわち「変形が途切れる」）場合が多くなり、結果的に $$R_{\overline{\rho}}^{\mathrm{univ}}$$ の形や次元に大きな制限がかかります。

> **重要事実:** $$\overline{\rho}$$ _が絶対既約で、_$$\mathrm{End}_{\mathbf{F}[G_K]}(\overline{\rho}) = \mathbf{F}$$_（自己準同型がスカラーしかない）という状況では、しばしば_ $$H^2(G_K,\mathrm{ad}(\overline{\rho}))$$ _が小さく（あるいは特定の制限下では0になることもあり）、障害がそれほど強くは働かないため、多様な変形が期待できる場合が多い。_

#### 具体例：次元の見積もり

たとえば $$K = \mathbf{Q}$$ で $$\overline{\rho}$$ が2次元の mod $$p$$ 表現かつ絶対既約であるとすると、

$$
H^1\bigl(G_{\mathbf{Q}}, \mathrm{ad}(\overline{\rho})\bigr)
$$

の次元は、しばしば分岐を許す素点（$$p$$を含む）などの数にだいたい対応します。もし有限個の素点以外で非分岐とし、$$p$$ に関してはたとえば「ordinary（半単純に上三角形になる）」といった条件を課すと、この次元が下がることがあります。楕円曲線に適用される設定などでは、この次元が程よい大きさになり、変形環の扱いが可能となります。

***

## 14.3 局所条件と大域的制約

### 14.3.1 局所的変形問題の定義

メイザーの手法の大きな特徴は、各素点 $$v$$ における表現の**局所的な条件**を柔軟に課せることにあります。例として：

1. $$v \mid p$$ **でのordinary条件:** $$ho_R\vert_{G_{K_v}}$$ が1次部分表現をもち、それが$$p$$進円分（cyclotomic）指標（あるいはそのねじり）に対応するように要求する（具体的には、行列を上三角にし、対角成分の一つがその円分指標になるなど）。これを _ordinary 変形_ と呼ぶ。
2. $$v \mid p$$ **での平坦（flat）/結晶（crystalline）性:** レイノー（Raynaud）の意味で有限平坦群スキームから来る表現（flat）や、フォンテーヌ–ラファイユ（Fontaine–Laffaille）の理論で定まる特定のホッジ–テイト重みをもつ結晶表現になる、などの条件を課すことができる。こうした局所条件を課すことで、可能な変形の空間は大幅に縮小される。
3. $$v \nmid p$$ **での分岐制約:** ある素点で非分岐であることを要求したり、特定の型（たとえばプリンシパル・シリーズ型やシュタインベルク型など）をとることを要求する。これら局所条件は対応する局所ガロワ群 $$G_{K_v}$$ に対する変形関手の形で定式化される。

このような局所条件を**大域的**に組み合わせると、元の普遍変形環の商として、**より次元の低い**普遍変形環が得られます。

$$
R_{\overline{\rho}}^{\mathrm{univ},\{\mathrm{loc\;conds}\}}
\;\cong\;
\frac{R_{\overline{\rho}}^{\mathrm{univ}}}{I}
$$

ここで $$I$$ は、各素点での局所条件を同時に満たすように導入した関係によるイデアルです。

### 14.3.2 パッチング（Patching）と大域変形環

各素点 $$v$$ において、制限表現 $$\overline{\rho}\vert_{G_{K_v}}$$ に対する **局所普遍変形環** $$R_v^{\mathrm{univ}}$$ を構成できるとします。すると大域的には、次のような戦略でこれらを「つなぎ合わせ」ます。

1. 各素点 $$v$$ において得られる局所変形環を、ある大域的普遍環 $$R_{\overline{\rho}}^{\mathrm{univ}}$$ に対応づけられるように整合させる（パッチング、あるいは補綴とも呼ばれる）。
2.  この過程を通して得られる大域的な商環

    $$
    R_{\overline{\rho}}^{\mathrm{univ},\mathrm{global}} 
    \;\;\cong\;\;
    R_{\overline{\rho}}^{\mathrm{univ}} \big/\! I
    $$

    において、すべての局所条件が同時に実現される。

こうした「パッチング」（または「補綴」や「インターポレーション」と呼ばれる）手法は、ワイルズやテイラー–ワイルズが「モジュラーリフティング定理（modularity lifting theorems）」を証明するうえで基礎となるものです。彼らは大域普遍変形環と、モジュラー形式の空間に作用する**Hecke代数**を比較し、両者が同型になる（有名な $$R = T$$ **定理**）ことを示します。この同型が得られると、尖点形式（cusp form）に付随するガロワ表現と、普遍変形環から得られるガロワ表現とが一致するため、もとの表現がモジュラー形式に対応することが証明されます。

***

### 14.3.3 歴史的背景と例

* **メイザーの初期の業績:** メイザーは1970年代に1次元ガロワ表現の研究でこの着想を得て、強力な新視点を切り開きました。その後、これが高次元にも拡張されました。
* **肥田（Hida）の理論:** 肥田は _ordinary_ なモジュラー形式の族を研究し、変形理論の変形版を用いて $$p$$進的変動（$$p$$-adic variation）を捉えました。
* **ワイルズのブレイクスルー:** ワイルズは2次元ガロワ表現（楕円曲線に付随するもの）のモジュラー性を示すため、変形環の手法を駆使しました。とくに、普遍変形環とHecke代数が完備交叉（complete intersection）として同じ次元をもち、しかも同型であるという「数値的一致」が、フェルマーの最終定理の証明の要になりました。
* **具体例：モジュラー形式の場合:** もし $$\overline{\rho}$$ が古典的モジュラー形式 $$f$$ に付随するガロワ表現を mod $$p$$ で落としたものだとすると、$$p$$ でのordinarity（上三角形になるなど）の条件を課すことは、局所表現がある特定の形（1次部分表現が円分指標）を持つことを意味します。このような局所条件を課すと、大域変形環の次元は下がり、$$p$$進モジュラー形式との密接な関係が保証されます。

***

## 14.4 結びと参考文献

変形理論は、**剰余ガロワ表現を連続的にゼロ標数の環へ持ち上げる**という視点を提供する強力で統一的な枠組みです。局所条件を普遍変形環に組み込むことで、考えうる無数の持ち上げを精密に取り扱うことができます。メイザーによって拓かれたこの視点は、フェルマーの最終定理の証明の中核をなした\*\*モジュラーリフティング定理（modularity lifting theorems）\*\*の基礎であり、今日に至るまで算術幾何学の最先端で広く活用されています。

### さらなる文献

1. **B. Mazur**. _Deforming Galois Representations_, in _Galois Groups over_ $$\mathbf{Q}$$, Springer, 1989.
2. **J.-P. Serre**. _Local Fields_, Graduate Texts in Mathematics, Springer, 1979.
3. **R. Taylor and A. Wiles**. _Ring-theoretic Properties of Certain Hecke Algebras_, Ann. of Math. (2) 141 (1995), 553–572.
4. **A. Wiles**. _Modular Elliptic Curves and Fermat’s Last Theorem_, Ann. of Math. (2) 141 (1995), 443–551.

続く節では、局所・大域のガロワコホモロジー条件が変形環とどのように相互作用するか、そしてこれらの環が「パッチング」手法や高度なホモトピー理論を使ってどのようにHecke代数と同一視されるかを解説します。これらの同一視（いわゆる $$R = T$$ **定理**）は、フェルマーの最終定理の証明の中心であり、現代代数的数論の柱ともいえる重要な結果です。
