# 第32節:整整数モデルと悪い還元の解析

***

## **第32節：整整数モデルと悪い還元の解析**

数論的対象としての楕円曲線や、より一般に数体上の代数曲線を研究する際、しばしば遭遇する概念として _整整数モデル (integral model)_ があります。これは、数体 $$K$$（しばしば $$K = \mathbb{Q}$$ とする）の整数環 $$\mathcal{O}_K$$ 上のスキームであり、$$K$$ 上で定義された（滑らかな）射影曲線を拡張したものです。特に、素イデアル（素数）で&#x306E;_&#x9084;元 (reduction)_ を調べると、その特別なファイバー（還元）が滑らかか、あるいは特異か（いわゆる**良い還元**あるいは**悪い還元**）という重要な性質が現れます。

こうした還元型を解析することは、曲線から得られる局所ガロワ表現の性質に大きく影響し、フェルマーの最終定理の証明における局所-大域対応の議論にも深く関わります。歴史的にも、フライ（Frey）の曲線やリベット（Ribet）のレベル下降定理に始まる流れが、ワイルズ（Wiles）やテイラー＝ワイルズ（Taylor–Wiles）による（半安定）モジュラー性の証明へと繋がった背景には、こうした還元の性質に基づく精密な手法があります。

この節では以下の内容を扱います。

1. 楕円曲線における **最小モデル (minimal model)** および **半安定モデル (semistable model)** の定義と、標数 $$p$$ における幾何学的退化の仕方
2. これらの概念をコンパクト化されたモジュライ空間の“境界成分”に結びつけ、安定モデルや半安定モデルで退化をどのように解釈するか
3. 整整数モデルやその還元型が局所ガロワ表現に与える制約、さらにフェルマーの最終定理の証明で用いられる “パッチング (patching) 議論” との関連

***

### 32.1 $$N$$ を割る素数での退化

$$\mathbb{Q}$$（またはより一般に数体 $$K$$）上の楕円曲線 $$E$$ を考え、その**伝導度 (conductor)** を $$N$$ とする。伝導度 $$N$$ は、楕円曲線 $$E$$ が“悪い還元”をもつ素数（イデアル）を正確に反映する不変量であり、$$N$$ を割る素数では $$E$$ は滑らかな還元をもたない。ここでは、そのような「悪い」素数においてどのような特異性が起こるか、なぜ特定のモデル（最小モデルや半安定モデル）が有用なのか、そしてそれが局所ガロワ表現の分岐にどのように関係するかを解説する。

#### 32.1.1 最小モデルと半安定モデル

**1. 整整数モデル**

**定義.**

楕円曲線 $$E$$ を $$K$$ 上に与えたとき、$$\operatorname{Spec}(\mathcal{O}_K)$$ 上の（平坦な）スキーム $$\mathcal{E}$$ で、その一般ファイバー（$$\operatorname{Spec}(K)$$ 上のファイバー）が $$E$$ と同型になるものを、$$E$$ の**整整数モデル (integral model)** と呼ぶ。具体的には、

$$
y^2 \;=\; x^3 + a_2 x^2 + a_4 x + a_6
$$

という形で $$K$$ 上与えられたワイエルシュトラス方程式の係数を、$$\mathcal{O}_K$$ の元に取り替えることで構成する。しかし、このときすべての素イデアルで「できるだけ良い性質（滑らかさ）」を保たせたいという課題がある。

**2. 最小ワイエルシュトラス方程式と最小モデル**

ワイエルシュトラス方程式は、変数変換（平方完成や $$x$$ の平行移動、拡大縮小など）によって、各素イデアル $$\mathfrak{p}$$ における係数の付値を“小さく”する操作が可能である。これ以上付値を下げることができなくなったとき、そのワイエルシュトラス方程式は**最小ワイエルシュトラス方程式**と呼ばれる。

**定義**

$$\operatorname{Spec}(\mathcal{O}_{K,\mathfrak{p}})$$ 上で、楕円曲線 $$E$$ を定める整整数モデル $$\mathcal{E}$$ が、他のどの整整数モデルよりも係数の付値が大きくならない（すなわち最小）ように選ばれているとき、$$\mathcal{E}$$ を$$E$$ の**最小モデル (minimal model)** という。

この操作を全素イデアルで同時に行うと、各局所で最小になっているモデルを貼り合わせたものを**大域最小モデル**という。ただし、場合によっては素ごとに最小になるようなモデルが両立せず、大域最小モデルが存在しないこともある。一方、局所的（1つの素 $$\mathfrak{p}$$ に対して）には常に最小モデルが存在する。

**3. 良い還元と悪い還元**

$$\mathfrak{p}$$ を $$\mathcal{O}_K$$ の素イデアルとし、その剰余体を $$\kappa(\mathfrak{p})$$ とする。

*   **良い還元 (good reduction)**: $$\mathcal{E}$$ の特別ファイバー

    $$
    \mathcal{E} \times_{\operatorname{Spec}(\mathcal{O}_K)} \operatorname{Spec}(\kappa(\mathfrak{p}))
    $$

    が$$\kappa(\mathfrak{p})$$ 上の滑らかな（非特異な）楕円曲線になるとき、$$E$$ は$$\mathfrak{p}$$ で良い還元をもつという。ワイエルシュトラス方程式の判別式 $$\Delta$$ を用いると、$$\Delta$$ が $$\mathfrak{p}$$ で 0 とならない（すなわち $$\mathfrak{p}$$ を割らない）ときに良い還元が得られる。
* **悪い還元 (bad reduction)**: 一方、特別ファイバーが特異になる（$$\mathfrak{p}$$ が $$\Delta$$ を割る）ときに悪い還元が生じる。悪い還元はさらに
  * **加法的 (additive)**（尖点をもつ特異ファイバー）
  * **乗法的 (multiplicative)**（節点をもつ特異ファイバー。split / non-split に分かれる） に分類される。

$$
\textbf{補足（Néron–Ogg–Shafarevichの判定）.}
$$

$$\mathfrak{p}\neq \ell$$（$$\ell$$ は 0 でない標数の素数を意味する）に対し、楕円曲線 $$E$$ の $$\ell$$ 進ガロワ表現が $$\mathfrak{p}$$ で非分岐 (unramified) であることと、$$E$$ が$$\mathfrak{p}$$ で良い還元をもつことは同値である。

**4. 半安定還元**

$$
\textbf{定義.}
$$

曲線（楕円曲線を含む）が $$\operatorname{Spec}(\mathcal{O}_{K,\mathfrak{p}})$$ 上で**半安定還元 (semistable reduction)** をもつとは、ある有限な拡大を施した後に、その特別ファイバーが（尖点をもたず）節点のみを特異点としてもつようなモデルを得られることをいう。

* 楕円曲線の場合、半安定還元とは特別ファイバーが滑らかか、あるいは乗法的（節点をもつ）3次曲線になることである。
* 古典的な例として **テイト曲線 (Tate curve)** があり、$$\mathbb{Q}_p$$ 上での $$q$$-展開を通じて乗法的（節点型）の還元を示す。

モジュラー性の証明、とりわけワイルズ (Wiles) の手法では、半安定性（良い還元ではなくてもよいが加法的還元はない状態）を仮定すれば十分な場合が多い（その後の一般化では加法的還元を含む場合にも対応する理論が発展している）。

**直感的背景**

* **最小モデル**は、付値を極力抑えた最も“経済的な”モデルであり、局所的な幾何学的退化を読み取りやすい。
* ある素イデアル $$\mathfrak{p}$$ で悪い還元が生じると、その局所ガロワ表現には必ず非自明な分岐が生じる。
* ワイルズのフェルマーの最終定理の証明においては、（良い還元でなくとも）**半安定**還元という仮定が要となった（その後はさらに一般の悪い還元を含むケースへ拡張がなされている）。

***

#### 32.1.2 境界成分と安定曲線

楕円曲線のモジュライ、たとえばモジュラー曲線 $$X_0(N)$$ を考えるとき、しばしば**尖点 (cusp)**（あるいはより一般の境界成分）を付け加えることでこれ&#x3092;_&#x30B3;ンパクト&#x5316;_&#x3059;る。このように付け加えられる“境界”は、「$$N$$ を割る素数での楕円曲線の退化」の情報をコーディングしている。

$$
\textbf{定義.}
$$

**安定曲線 (stable curve)** とは、射影曲線であって特異点が**節点 (node)** のみ、自己同型群が有限であるものをいう。デルigne＝マンフォード (Deligne–Mumford) 理論では、離散付値環上の滑らかな曲線族は、有限拡大後に**半安定**あるいは**安定**モデルに拡張できる。

1. **安定還元定理 (Stable Reduction Theorem)**: 離散付値環 $$R$$ の分数体上で定義された滑らか・射影・幾何学的に連結な曲線 $$X$$ は、$$R$$ を有限拡大することにより、**半安定（および安定）モデル**をもつ。
2. **境界成分**: モジュラー曲線 $$X_0(N)$$ の場合、コンパクト化で付け加わる点（尖点）は、レベル構造付き楕円曲線の“退化”を表している。これは上半平面における「$$\Gamma_0(N)$$ の無限遠点の軌道」に対応し、標数 $$p$$ で見れば、節点型の曲線などが典型例となる。

**例：判別式から見る悪い還元**

$$\mathbb{Q}$$ 上の楕円曲線

$$
y^2 \;=\; x^3 + A x + B
$$

を考える。判別式を

$$
\Delta \;=\; -16\bigl(4A^3 + 27B^2\bigr)
$$

とおくと、素数 $$p$$ に対し

* $$p \nmid \Delta$$ であれば、$$E$$ は **良い還元** をもつ。
* $$p \mid \Delta$$ であれば、$$E$$ は **悪い還元** をもつ。

さらに、$$\Delta$$ が $$p$$ でどう因数分解するかを調べると、乗法的か加法的かの別がわかる。半安定の場合（乗法的）には特別ファイバーに節点が現れ、加法的な場合には尖点が現れる。

歴史的には、小平 (Kodaira) とネロン (Néron) によって楕円曲面の**特異ファイバー**が分類されており、$$I_n, I_n^*, II, II^*, \dots$$ といった記号で幾何学的かつ数論的な性質が整理されている。

***

### 32.2 ガロワ変形への帰結

ここからは、良い／悪い還元などの幾何学的像を**局所ガロワ表現**の文脈で捉える。これはワイルズによるフェルマーの最終定理の戦略や、より広範な $$\mathrm{GL}_2$$ におけるラングランズ・プログラムの要請と深く結びついている。

#### 32.2.1 悪い還元が局所表現に与える制約

$$
\textbf{定義（楕円曲線に付随するガロワ表現）.}
$$

$$\mathbb{Q}$$ 上の楕円曲線 $$E$$ に対し、各素数 $$\ell$$ に対して $$\ell$$ 進テイト加群 $$T_\ell(E)$$ は

$$
\rho_{E,\ell} : G_{\mathbb{Q}} \;\to\; \mathrm{GL}_2\bigl(\mathbb{Q}_\ell\bigr)
$$

という2次元の $$\ell$$ 進ガロワ表現を与える。素数 $$p \neq \ell$$ における分解群への制限 $$ \rho_{E,\ell}|_{G_{\mathbb{Q}_p}}$$ を見ると、

* **良い還元**をもつ場合、多くの場合この局所表現は**非分岐 (unramified)** となる。
* **悪い還元**をもつ場合には、表現が**分岐 (ramified)** を起こす。特に“乗法的”か“加法的”かで分岐の仕方（おとなしい (tame) か激しい (wild) か、半安定かどうかなど）が異なる。

$$
\textbf{定義（アルティンの位数 (Artin conductor)}.
$$

局所ガロワ表現の分岐の度合いを測る不変量に**アルティンの位数 (Artin conductor)** がある。楕円曲線 $$E$$ の伝導度 $$N$$ は、これら局所アルティンの位数を素数ごとに組み合わせたものであり、結局 $$p$$ でのガロワ表現が非自明に分岐する（＝悪い還元）のは、$$p$$ が $$N$$ を割るときに限る。

**変形理論への含意**

$$\rho_{E,\ell}$$ &#x306E;_&#x5909;形 (deformation)_ を考えるワイルズ＝マズール (Wiles–Mazur) やテイラー＝ワイルズ (Taylor–Wiles) の枠組みでは、各素数 $$p$$ が課す局所条件が変形やリフティングの可能性を制約する。たとえば、$$p$$ で$$E$$ が半安定ならば、局所ガロワ表現に「シュタインベルク (Steinberg) 型」あるいは「単元的 (unipotent)」な振る舞いを課し、$$p$$ で良い還元ならば（$$\ell = p$$ の場合はクリスタリン (crystalline) なども含め）「非分岐」条件が課される。悪い還元は分岐を生むため、これを取り扱うことがレベル下降（リベットの定理など）やパッチング法に不可欠なステップとなる。

***

#### 32.2.2 整整数モデルとパッチング議論

$$(R = T)$$ 法（変形環とHecke代数の同一性を示す典型的な方法）のおおまかな流れを想起しよう（詳細は前の節を参照）:

1. ある既約な mod $$\ell$$ ガロワ表現のリフト（変形）を分類する「**変形環** $$R$$」を構成する。ここで素数ごとに課す局所条件が変形環を決める。
2. 一方、局所固有値データを符号化したモジュラー形式の「**Hecke代数** $$T$$」を考える。
3. それぞれの有限商環が一致すること（パッチング議論）を示すと、最終的に $$R \simeq T$$ が従い、元のガロワ表現がモジュラー形式から来ることが分かる。

**ここで「悪い還元」と整整数モデルが登場するのはなぜか？**

* **幾何** $$\to$$ **代数への橋渡し**: 素数ごとの還元型という局所幾何学的データが、そのまま局所ガロワ表現の型（非分岐・シュタインベルク・特異分岐など）を規定する。特に、最小・半安定モデルがある素イデアルでの還元型をはっきりと示してくれる。
* **境界情報**: コンパクト化されたモジュライ空間（$$X_0(N)$$ など）における境界成分（尖点）は、局所的に退化した楕円曲線を表しており、これは局所条件の設定とほぼ同義。
* **パッチング**: 局所的な変形環（還元型に対応する変形条件を課した環）を貼り合わせる際、悪い還元の情報こそが局所因子を決定する鍵となる。

**歴史的背景**

アンドリュー・ワイルズ (Andrew Wiles) のフェルマーの最終定理の証明では、

* 小さな素数で特異還元をもつような**Frey曲線 (Frey curve)** の考察
* **リベット (Ribet)** のレベル下降定理（ある種の素数を伝導度から除去できること）
* 局所変形条件（たとえば半安定性）によるガロワ表現変形環の取り扱い

といった流れが重要な役割を担った。これらはいずれも、**整整数モデル**と**還元型**を厳密に把握することで「局所表現がどうなるか」を確定させ、それを大域変形の理論に組み込む構造となっている。

***

### 第32節 まとめ

1. **悪い還元を解析する意義**
   * 局所ガロワ表現の型（非分岐か、あるいは乗法的・加法的・半安定的分岐か）を見極める上で必須。
   * 伝導度 $$N$$ に直接関わるため、モジュラー形式との対応（フーリエ係数やHecke作用素）にも大きく作用する。
2. **最小モデルと半安定モデル**
   * **最小モデル**は、付値を最小化することで局所的退化を“純粋化”して捉えるために便利。
   * **半安定性**（尖点を除き節点のみ）という仮定は、強力な変形論・モジュラー性定理を適用する最小限の要件になり得る。
3. **モジュライの境界成分**
   * コンパクト化されたモジュライ空間（$$X_0(N)$$ など）の境界は、レベル構造付き楕円曲線の“退化型”を示す。
   * 特に尖点に対応する退化は、局所ガロワ表現における乗法的還元型などを反映している。
4. **局所-大域の相互作用**
   * 1つ1つの素（イデアル）での幾何学的還元型が、局所ガロワ表現へと結びつく（局所データ）。
   * それらを “パッチング” によってグローバルな変形環へと貼り合わせることで、モジュラー性やフェルマーの最終定理が証明される流れが形作られる。

このように、_整整数モデルと悪い還元_ を詳細に分析することは、単なる技術的作業ではなく、ガロワ表現をコントロールしモジュラー性を示すうえで極めて本質的なステップである。

***

#### 参考文献

* **Silverman, J. H.** _The Arithmetic of Elliptic Curves_. Springer.\
  （最小モデルや還元型、ガロワ表現の基礎的事項を包括的に解説）
* **Deligne, P. & Mumford, D.** (1969). _The irreducibility of the space of curves of given genus_. IHÉS Publ. Math.\
  （安定曲線のコンパクト化理論）
* **Néron, A.** (1964). _Modèles minimaux des variétés abéliennes sur les corps locaux et globaux_.\
  （アーベル多様体のNéronモデルに関する古典的研究）
* **Serre, J.-P. & Tate, J.** (1968). _Good reduction of abelian varieties_. Ann. Math.\
  （良い還元と非分岐ガロワ表現を結びつける基本的定理）
* **Kodaira, K.** (1963). _On compact analytic surfaces II–III_. Ann. Math.\
  （楕円曲面の特異ファイバーの分類）

これらの文献は、幾何と数論の交差領域で確立された基礎理論を提供し、最終的に**フェルマーの最終定理**の解決にも大きく寄与した。
