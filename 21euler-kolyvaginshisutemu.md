# 第21節:Euler-Kolyvaginシステム

**Euler（コリヴァギン）システム**（_Kolyvagin–Rubin システ&#x30E0;_&#x3068;呼ばれることもある）は、現代数論の強力な枠組みの一つです。これは **ガロワ表現のセルマー群を制御・評価** する手段を与え、楕円曲線や $$L$$-関数など中心的対象の深い算術的性質を導くのに寄与します。本節では、具体的な例や関連定理、歴史的背景も交えながら、その主要なアイデアを展開します。

***

## 21.1 定義と例（コリヴァギン–ルビン）

### 21.1.1 直観的概要

**Euler システム**とは、（しばしば平方自由整数に制限される）正の整数 $$n$$ に添字づけられたガロワ・コホモロジー類の整合的な族 $$\{\kappa_n\}$$ を指します。これらの類は、しばしば $$H^1(\mathrm{Gal}(\overline{\mathbb{Q}}/K_n), M)$$ のようなコホモロジー群に属し、ここで $$K_n$$ は整数 $$n$$ と関連づいた数体、$$M$$ は楕円曲線などから得られるガロワ加群です。決定的なのは、これらの類が**ノルム適合性**（norm compatibility）と呼ばれる関係を満たす点であり、これはさまざまな拡大間での大域的な算術的パターンを反映します。

1. **古典的なオイラー積との類推**\
   “Euler”という名称は、$$L$$-関数を局所的成分に分解するオイラー積 $$\prod_{p} (1 - a_p p^{-s} + \cdots )^{-1}$$ と対応をもつことに由来します。Euler システムでも同様に、素数やそのべきごとにクラスを整合的に配置する“局所から大域へ”という関係がノルム写像を通じて成立します。
2. **必要性**
   * **セルマー群の評価**: セルマー群は有理点やその他の算術的現象の障害をエンコードします。Euler システムのノルム関係の組合せにより、コホモロジー類が消滅したり、強い可除性（divisibility）の制約を受けたりするので、セルマー群の大きさ（あるいはランク）を制限できます。
   * $$L$$**-関数の特殊値との関係**: 歴史的にも多くの Euler システムは、$$L$$-関数の整数点での値や、モジュラー・シムラ多様体上の「特別な点」から構成されます。
   * **主要な予想への影響**: セルマー群を制御する手法は、バーク–スウィンナートン＝ダイアー予想 (BSD) や岩澤主予想といった大きな予想の部分的な結果に不可欠であり、楕円曲線のモジュラー性を通して**フェルマーの最終定理**の証明にも影響を与えています。
3. **主要な人物**
   * **V. コリヴァギン (Victor Kolyvagin)** は、楕円曲線のランクや有限性に対する結果を得るために、この枠組みを最初に確立しました。
   * **K. ルビン (Karl Rubin)** は、サイクロトミック・ユニットやエレファンティン（楕円）ユニット、ヒールナー点など、より広いクラスの Euler システムを構築し、岩澤理論における強力な応用例を提示しました。

***

### 21.1.2 基本的（しかし典型的な）例: サイクロトミック Euler システム

ヒールナー点や楕円曲線に入る前に、より初歩的な例としてしばしば取り上げられるのは**サイクロトミック・ユニット**に基づく Euler システムです。

1. **サイクロトミック拡大**\
   ある素数 $$p$$ に対し、$$p^n$$-乗根の1つである原始根 $$\zeta_{p^n}$$ を含む $$\mathbb{Q}(\zeta_{p^n})$$ を考えます。これはサイクロトミック拡大と呼ばれます。
2. **サイクロトミック・ユニット**\
   これらの拡大では $$(1 - \zeta_{p^n})$$ のよう&#x306A;_&#x30B5;イクロトミック・ユニッ&#x30C8;_&#x304C;構成され、それらは単数群（ユニット群）の有限指数部分群を生成します。
3. **ガロワ・コホモロジー類**\
   単数とコホモロジーを結びつける **Kummer 写像** を介して、$$\mathbb{Q}(\zeta_{p^n})$$ 上の $$\mu_{p^n}$$ に値をとるコホモロジー群 $$H^1(\mathbb{Q}(\zeta_{p^n}), \mu_{p^n})$$ にサイクロトミック・ユニット由来の類を得ることができます。ノルム写像による $$\mathbb{Q}(\zeta_{p^m})$$ への押し出し（corestriction）との対応が、これらの類に厳密な整合性を与えます。

こうして得られる **サイクロトミック・コホモロジー類** は、最初期から知られる Euler システムの一例であり、素朴に見えるノルム関係が、実は類数や $$p$$-進 $$L$$-関数に対する深い制限を与える仕組みをよく示しています。

***

### 21.1.3 モジュラー曲線上の特別な点（ヒールナー点）による構成

サイクロトミック・ユニットは Euler システムの最初の味見のような例ですが、楕円曲線やバーク–スウィンナートン＝ダイアー予想との関係で最も重要となる構成は、モジュラー曲線上の**特別な点 (special points)** を用いる方法です。なかでも **ヒールナー点 (Heegner points)** は代表的な入り口です。

1. **CM点**
   * モジュラー曲線 $$X_0(N)$$ 上の _CM点_ は、虚二次体 $$K$$ の**複素乗法** (complex multiplication) をもつ楕円曲線（ある種のレベル構造付き）をパラメータ化するときに現れます。
   * ヒールナー点は、このパラメータ空間上の特別な切断（あるいは断面）を与え、しばしばある作用素下で消滅（または部分的に消滅）する代数的数を生み出します。
2. **体の塔**
   * ヒールナー点を生成するような正方自由整数 $$n$$ に応じて、$$K_n$$ と呼ばれる拡大（環のクラスタイプ拡大）を考えます。
   * 各 $$K_n$$ において、ヒールナー点に付随するコホモロジー類 $$\kappa_n$$ を得ます。これは楕円曲線に付随する $$\ell$$-進表現や、そこから誘導される加群の 1次ガロワ・コホモロジーに属します。
3. **ノルム関係**
   * $$m$$ が $$n$$ を割るとき、拡大 $$K_n / K_m$$ が存在します。そこでのヒールナー点（および対応するコホモロジー類）は、ノルム写像や制限・押し出し写像を通じて整合的に関連づけられます。
   * これがまさに Euler システムの特徴であり、$$\kappa_n$$ と $$\kappa_m$$ を結ぶ**明示的なノルム適合性**を満たします。

歴史的には、**ヒールナー点**に基づく Euler システムは、コリヴァギンによる楕円曲線 $$E/\mathbb{Q}$$ のランク評価に決定的な役割を果たしました。

***

### 21.1.4 コリヴァギンの方法とその帰結

コリヴァギンの画期的なアイデアは、Euler システムを用いてセルマー群上のある種のクラスを**消滅させる**（あるいは可除性を強く課す）ことにあります。

> **主要定理（コリヴァギンの着想、非形式的説明）**\
> $$\{\kappa_n\}$$ が楕円曲線 $$E/\mathbb{Q}$$ に付随するガロワ表現のコホモロジーで非自明な Euler システムであるとき、これらの類はセルマー群の多くの元に厳しい可除性条件を課すため、そのサイズ（あるいは次元）が極めて小さくなる（消滅に近い）ことを強制する。

もう少し正確に言えば、$$\kappa_n$$ と $$H^1(\mathbb{Q}, V)$$（ここで $$V$$ はしばしばその双対表現に関係する $$\ell$$-進表現）に属するクラスとのペアリングを考えると、ある局所条件の下でこのペアリングの消滅が生じ、結果としてセルマー群の次元に上限が設定されることになります。これは楕円曲線のランクや有限性に強い制限を与える基盤です。

***

## 21.2 セルマー群を Euler システムで評価する

### 21.2.1 セルマー群：定義と文脈

$$\mathbb{Q}$$ 上の楕円曲線 $$E$$ に対して、素数 $$\ell$$ ごとに

$$
V_\ell(E) \;=\; \Bigl(\varprojlim_n E[\ell^n]\Bigr) \otimes_{\mathbb{Z}_\ell} \mathbb{Q}_\ell
$$

という $$\ell$$-進ガロワ表現を考えることができます。**セルマー群** $$H^1_f(\mathbb{Q}, V_\ell(E))$$（あるいは古典的には $$\mathrm{Sel}(\mathbb{Q}, E[\ell^\infty])$$ と書かれる）とは、特定の素で分岐を許さない、もしくは $$\ell$$ に対応する素で適切な部分空間に属する、といった**局所条件**で定義された 1次コホモロジー群の部分群です。

平易に言えば、セルマー群は「大域的な点」に由来するようなコホモロジー類（あるいはその捻れや拡大データ）を捉えており、そのランクは有理点 $$E(\mathbb{Q})$$ のランクと深く結びついています。つまり、セルマー群が有限であることを示すことは、しばしば **Mordell–Weil 定理**における有限生成性やランク評価の重要な一歩となります。

### 21.2.2 メカニズム：ノルム適合性 $$\implies$$ アンニヒレーター（零化子）

1.  **ノルム関係**\
    各整数 $$n$$ とその約数 $$m$$ に対し、Euler システムの類は

    $$
    \mathrm{cor}_{K_n/K_m}(\kappa_n) \;=\; \alpha_{n,m}\,\kappa_m
    $$

    という形式の関係を満たします（$$\mathrm{cor}$$ は群コホモロジーにおける押し出し（corestriction）作用）。ここで $$\alpha_{n,m}$$ は明示的に与えられる因子です。これが Euler システムの**背骨**ともいえる構造です。
2. **局所–大域ペアリング**\
   局所 Tate 双対性や Poincaré–Tate 双対性によって、$$H^1(\mathrm{Gal}(\overline{K}/K), V)$$ の元は $$H^1(\mathrm{Gal}(\overline{K}/K), V^*)$$ の元と対をなすペアリングを持ちます。もし $$\kappa_n$$ が非零ならば、このペアリングが大きな部分空間上で消滅することを導き、多くのコホモロジー類が除外されてセルマー群の余地が小さくなるのです。
3. **セルマー群の評価**\
   仮にセルマー群が“過大”であるとすると、Euler システムの非消滅性や特定の因子構造と矛盾する場合が多く、この矛盾からセルマー群のランクに上限がかかります。これにより $$\mathrm{rank}(E(\mathbb{Q}))$$（あるいは $$\mathrm{Sha}(E/\mathbb{Q})$$ の有限性）が結論づけられるわけです。

#### 定理（コリヴァギンのセルマー群評価、非形式的）

> $$E$$ _を_ $$\mathbb{Q}$$ _上の楕円曲線とし、適切なヒールナー点ベースの Euler システム_ $$\{\kappa_n\}$$ _が存在して非自明とする。すると、これらの類が無数の平方自由整数_ $$n$$ _で非零になる場合、_$$E$$ _のセルマー群は有限個の素を除いて**有界**であり、しばしばランク_ $$\le 1$$ _になることが導かれる。さらに追加仮定（_$$L(E,1)$$ _の非消滅など）があれば、**シャファレヴィッチ–テイト群**_ $$\text{Ш}(E/\mathbb{Q})$$ _**の有限性**や_ $$E(\mathbb{Q})$$ _のランクの決定にもつながる。_

これはあくまで簡略化した言い方ですが、ヒールナー点などの特別値や特別点が、どのようにして **ランク** と **有限性** の主張へと結びつくか、その本質を示しています。

***

## 21.3 岩澤理論との関係

### 21.3.1 $$p$$-進 $$L$$-関数と主予想

Euler システムは **岩澤理論** と不可分に結びついており、特に $$\mathbb{Z}_p$$-拡大での数論的不変量の増大を追う研究で重要です。岩澤理論の「主予想」は、ある加群の特性イデアルと $$p$$-進 $$L$$-関数を結びつけるもので、次のように Euler システムが主要な役割を果たします。

* **Euler システムからの構成**: 多くの $$p$$-進 $$L$$-関数は Euler システム（とくにサイクロトミック・ユニット系など）から構成されるか、少なくともこれらにより**制約**を受けます。サイクロトミック Euler システムは古典的な**岩澤主予想**（サイクロトミック体の類数と $$\mu$$-不変量など）を証明する要として機能します。

### 21.3.2 コントロール定理

$$\mathbb{Q}_\infty$$ を $$\mathbb{Z}_p$$-拡大とするとき、Euler システムは有限階数 $$\mathbb{Q}_n$$ のセルマー群と無限階数の“極限セルマー群”を比較する**コントロール定理**の確立にも用いられます。

1. **分岐しない素**: 分岐しない素では、Euler システムによるノルム適合性が層状に維持されます。
2. **素の分岐**: $$\mathbb{Q}_\infty$$ で分岐する素の振る舞いも、局所条件を通じてセルマー群の定義に影響を与えます。
3. **帰納極限および逆極限**: ノルム関係が慎重に整備されているため、ある有限段階で生じたクラスの消滅や制限が、無限段階でも維持されることが示され、最終的に大域的セルマー群の構造へと結びつきます。

***

## 21.4 計算例と歴史的メモ

### 21.4.1 代表的計算：導体 $$N$$ の楕円曲線に対するヒールナー点

古典的で重要な計算例を示します。

* **セッティング**: $$\mathbb{Q}$$ 上の楕円曲線 $$E$$（導体 $$N$$）を取り、虚二次体 $$K$$ を選ぶ。ここで $$N$$ の素因子が $$K$$ で分解する（あるいは局所条件を満たす）とする。
* **ヒールナー点**: モジュラー曲線 $$X_0(N)$$ 上の CM点 $$x_K$$ を考え（これは $$K$$ の複素乗法をもつ楕円曲線に対応）、モジュラーパラメトリゼーション $$\phi: X_0(N) \to E$$ を通して得られる $$E$$ 上の点 $$y_K$$ をヒールナー点と呼ぶ。
* **塔の構成**: 平方自由整数 $$n$$ ごとに、$$K$$ の環のクラスタイプ拡大 $$K_n$$ を考え、そこに付随するヒールナー点 $$y_{K_n}$$ を得る。
* **Kummer 画像**: $$\ell$$-冪倍との組み合わせで Kummer 写像を適用すると、$$H^1(\mathrm{Gal}(\overline{\mathbb{Q}}/K_n), V_\ell(E))$$ 内の類 $$\kappa_n$$ が得られる。
* **ノルム関係**: コリヴァギンの仕事で、$$\kappa_n$$ と $$\kappa_m$$（$$m|n$$ のとき）の間に明示的な関係式が確立される。この族 $$\{\kappa_n\}$$ こそが Euler システムをなし、セルマー群を消滅や可除性により「圧縮」していく。

### 21.4.2 計算的視点

次元の低い場合（小さな導体など）では、より直接的に:

* **ヒールナー点の同定**: $$y_K$$ を具体的に代数座標で求められる場合がある（環のクラスタイプ拡大内での計算）。
* **非消滅の確認**: ある種の $$n$$ に対して $$\kappa_n \neq 0$$ であることを理論的・数値的に検証できる。
* **結論**: それにより $$\mathrm{rank}(E(\mathbb{Q}))$$ が 0 あるいは 1 であること、シャファレヴィッチ–テイト群の有限性などが示される。

こうした具体的検証は、小さな導体の楕円曲線を対象に幾つも行われ、コリヴァギンの方法が実際にどれほど強力かを示す好例となっています。

### 21.4.3 歴史的モニュメント

* **コリヴァギン (1980年代後半)**: ヒールナー点を楕円曲線のランク評価に応用し、シャファレヴィッチ–テイト群 $$\text{Ш}(E/\mathbb{Q})$$ の有限性を、ある状況下で初めて**無条件**で証明。
* **ルビン**: このアイデアをさらに一般化し、_Euler システム_ の概念的基盤を確立（ヒールナー点やサイクロトミック・ユニットに限られない広い射程を与えた）。
* **メイザー–ワイルズ (Mazur–Wiles)**: サイクロトミック Euler システムを用いて、$$\mathbb{Q}$$ の可換拡大の類体を扱い、**岩澤理論**の分野を大きく進展させた。

***

## 21.5 この概念が重要な理由

1. **局所データと大域的情報の結びつき**\
   Euler システムは、素ごと・階層ごとに定義されるクラスをノルム写像で繋げることにより、局所的制約が大域的構造（セルマー群やランク、トーショングループ）に大きな影響を与えるという原理をはっきり示します。
2. **主要予想への応用**
   * **バーク–スウィンナートン＝ダイアー (BSD)**: $$L(E,1)\neq 0$$ のときにランク 0 や 1 を示すなど、Euler システムは BSD の多くの重要な部分結果に寄与。
   * **岩澤主予想**: サイクロトミック・ユニット系などからなる Euler システムは、$$p$$-進 $$L$$-関数とモジュールの特性イデアルの等価を示すうえで中心的役割を果たす。
3. **有限生成性と有限性の確立**\
   Euler システムが非自明な場合、それはガロワ・コホモロジー群（やセルマー群）が有限ランクどころか**有限**であることに結びつく場合が多いです。楕円曲線においては、シャファレヴィッチ–テイト群の有限性を示す有力な手段となります。
4. **フェルマーの最終定理との関連**\
   アンドリュー・ワイルズの証明は主にモジュラー性や変形理論に依拠していますが、モジュラー形式やガロワ表現、$$L$$-関数の特別値の算術を理解するうえで、Euler システムの考え方は並行して大きな影響を与え続けています。

***

## 21.6 結論と展望

**Euler（コリヴァギン）システム**は、**ガロワ・コホモロジー**や**セルマー群**から **岩澤理論**、そして\*\*$$L$$-関数の特殊値**に至るまで、現代数論の多様な分野を結びつける総合的な枠組みです。そのノルム適合性というコアアイデアは、コホモロジー群の大部分を**消滅\*\*させたり強い制限をかけることで、楕円曲線や類数問題などのランクやトーショングループに関する決定的な情報を与えます。

今後は、本節（第21節）で述べた手法が、（例えば第14節の**変形環**や第15節のより深いセルマー群の計算など）さらに別の手法と結びついて、**長年のディオファントス的課題**を攻撃する強力なツールキットを形成していきます。バーク–スウィンナートン＝ダイアー予想の中心的ケースや、ラングランズ・プログラムの中心にある予想の一部に対するアプローチは、こうした手法が統合されることで一段と進む可能性があります。

***

## 21.7 推薦文献

* **V. Kolyvagin**, _Finiteness of_ $$E(\mathbb{Q})$$ _and_ $$\text{Ш}(E,\mathbb{Q})$$ _for a subclass of Weil curves_, _Math. USSR Izv._ (1990).
* **K. Rubin**, _Euler systems_, Annals of Mathematics Studies, Princeton University Press.
* **B. Mazur and A. Wiles**, _Class fields of abelian extensions of_ $$\mathbb{Q}$$, _Invent. Math._ (1984).
* **J. Coates and R. Sujatha**, _Cyclotomic Fields and Zeta Values_, Springer （サイクロトミック Euler システムの入門的解説として推奨）。

これらの文献では、**理論的基盤**（コホモロジー理論や岩澤主予想など）とともに、**具体例**（ヒールナー点、サイクロトミック・ユニット、エレファンティン・ユニットなど）の構成と応用例がより詳しく解説されています。Euler（コリヴァギン）システムの威力が、算術幾何の広範な領域でいかに発揮されるかを知るには不可欠の読み物です。

***

**（本節終わり）**
