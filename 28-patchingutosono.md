# 第28節: パッチング論法とその応用

近代数論の大きな成果の一つは、アンドリュー・ワイルズ（後にリチャード・テイラーとの共同研究）による、$$\mathbb{Q}$$ 上の半安定（semistable）楕円曲線に対する谷山–志村–Weil予想の証明です。そして、この結果からフェルマーの最終定理（FLT）が系として得られます。

ワイルズの業績における中心的な新手法が、いわゆる **パッチング論法 (patching argument)** です。大まかに言うと、「パッチング (patching)」とは、無限にわたる体の塔を通して、各局所（ローカル）データを厳密に整合させながら一つの大域的（グローバル）ガロア表現を「つなぎ合わせる (patch)」ことを指します。本節では、以下の点を概観します。

1. 主な技術的基盤――**逆極限**、**制御定理**、および**ガロアコホモロジー**（\S 28.1）
2. いわゆる $$R \cong T$$ 同型の要点（\S 28.2）。ここで $$R$$ は普遍変形環（universal deformation ring）、$$T$$ は適切に局所化したHecke代数を表す。
3. **モジュラー楕円曲線**と**フェルマーの最終定理**への最終的帰結（\S 28.3）

最後に、歴史的・概念的な考察や、パッチング論法の雰囲気を掴むための簡単な例を述べます（ただし深い技術的詳細には立ち入りません）。

***

## **28.1 逆極限、制御定理、そしてコホモロジー**

### **28.1.1 直観的概観**

$$R \cong T$$ を証明するうえで大きな障害となるのは、1つの環上の1つの表現だけを扱うわけではないという点です。むしろ、_無限&#x5854;_&#x3092;通じて、_局所条&#x4EF6;_&#x3092;指定しつつ変形（deformation）のファミリー全体を扱う必要があります。たとえば、$$p$$ 進サイクロトミー拡大の高い層へ制限していくような状況が典型例です。これを制御するための鍵は次の通りです。

* **逆極限の枠組み**: 有限段階で定義されたデータを「逆極限」オブジェクトへと帰着させる仕組み。
* **制御定理 (Control Theorems)**: （主に Mazur の研究に端を発する）コホモロジー的なデータ（次元やランクなど）が、塔を上がっていっても無制限には複雑化せず、予測可能な挙動を示すことを保証する定理群。

この「予測可能性」がなければ、局所変形を大域的表現へ組み上げる（patching する）ことが体系的にできません。

### **28.1.2 逆極限と帰納的パッチング**

#### **定義 28.1（逆系と逆極限）**

$$\{R_n\}_{n\in\mathbb{N}}$$ を、_遷移写像_ $$\varphi_{n+1,n}\colon R_{n+1} \to R_n$$ が与えられた環（あるいは加群）の族とする。もし $$m < n$$ のとき $$\varphi_{m,n}\circ \varphi_{n+1,m} = \varphi_{n+1,n}$$ が成り立つならば、$$\{(R_n,\varphi_{n+1,n})\}$$ を**逆系 (inverse system)** と呼ぶ。**逆極限** $$\varprojlim R_n$$ とは、各 $$\varphi_{n+1,n}$$ によって互換的な列 $$(r_1, r_2, \dots)$$ 全体の集合に、成分ごとの環（あるいは加群）演算を与えたものである。

典型例としては以下がある。

*   **サイクロトミー塔**: ある素数 $$p$$ に対して、原始 $$p^n$$ 乗根 $$\zeta_{p^n}$$ を含む体 $$\mathbb{Q}(\zeta_{p^n})$$ を考えると、

    $$
    \mathbb{Q} \;\subset\; \mathbb{Q}(\zeta_p) \;\subset\; \mathbb{Q}(\zeta_{p^2}) \;\subset\; \cdots
    $$

    のように拡大が続く塔がある。各有限拡大に付随するコホモロジー的データや変形は、制限写像（あるいは核制限写像）によって結び付けられ、逆系を形成する。

**帰納的（あるいは上昇的）パッチング**の典型的手順:

1. **仮定**: ある段階 $$n$$ で両立する変形（あるいは表現）を持っているとする。
2. **拡張**: それを段階 $$n+1$$ に引き上げる。この際、段階 $$n$$ での局所条件をより精密化する形で与える。
3. **整合性の確認**: すべての段階で「貼り合せ（patch）」が互いに矛盾しないようにチェックする。

最終的には、このような段階の上昇を無限に繰り返した極限として、大域的ガロア表現（無限に多くの素点での局所条件を課したもの）が存在し、所望の性質（たとえばモジュラー表現に一致するなど）をもつことを示す。

### **28.1.3 ガロアコホモロジーにおける制御定理**

#### **定義 28.2（セルマー群の概略）**

ガロア表現 $$\rho\colon G_{\mathbb{Q}} \to \mathrm{GL}_2(\overline{\mathbb{Q}}_p)$$ が与えられたとき、**セルマー群 (Selmer group)** $$\mathrm{Sel}(\rho)$$ とは、大域コホモロジー群 $$\mathrm{H}^1(\mathbb{Q}, \rho)$$ の部分群であって、各素点における「セルマー条件」（非分岐、あるいは “ordinary” などの条件）を満たすように制限されるものを指す（形式的には、局所部分群が特定の部分空間に入るように課す）。

**制御定理 (Control Theorems)** は、このようなコホモロジー群、特にセルマー群などの次元や構造が、サイクロトミー拡大などの「良い性質」をもつ無限塔を上がっていったときに安定する、あるいは変化が制御された形でしか起きないことを保証する。具体的に言えば、$$\Gamma_n = \mathrm{Gal}(\mathbb{Q}(\zeta_{p^n})/\mathbb{Q})$$ として、$$\mathrm{H}^i(\Gamma_n, \rho)$$ と $$\mathrm{H}^i(\Gamma_{n+1}, \rho)$$ を比較するような際、ある段階から先は次元が安定する、あるいは予測可能なランク差しか生じない、などの結論が得られる。

Mazur に帰される古典的な定式化（の簡略版）は次のようになる。

> **定理 28.3（Mazurの制御定理：簡単化版）**\
> $$M$$ _を、サイクロトミー拡大上で「ordinary」という性質をもつガロア加群とする。すると、ある整数_ $$n_0$$ _が存在して、すべての_ $$n \ge n_0$$ _に対して、_$$\mathrm{H}^1(\Gamma_n, M)$$ _の_ $$\mathbb{F}_p$$_-次元は一定（あるいは決まったランク変化）となる。_

この安定性こそが、局所変形条件が高次の拡大で際限なく複雑化しないことを意味する。したがって、無限塔を通じて変形を「パッチング」し、大域的表現を作り上げることが可能になる。

***

## **28.2 いよいよ核心へ：**$$R \cong T$$

パッチング論法の最終的な目標は、次の同型を示すことである。

> **定理 28.4** $$(R \cong T)$$\
> $$\overline{\rho}$$ _を（たとえば半安定楕円曲線から生じるような）適当な剰余ガロア表現とする。各素点で課される局所条件を満たす普遍変形環を_ $$R$$ _とし、同じくその剰余表現に対応するように局所化したHecke代数を_ $$T$$ _とする。このとき、以下の環同型が成り立つ。_
>
> $$
> R \;\cong\; T.
> $$

以下では、この結論がパッチング論法によってどのように導かれるかを概観する。

### **28.2.1 Hecke代数と普遍変形：キーポイント**

1. **Hecke代数** $$T$$:\
   レベル $$N$$・重さ2（FLT 文脈で典型）における尖点形式（cusp forms）の空間 $$S_2(\Gamma_0(N))$$ を考える。ここに古典的Hecke作用素 $$T_\ell$$（素数 $$\ell$$ に対応）が作用するので、**Hecke代数** $$\mathbf{T} = \mathbb{Z}[\dots, T_\ell, \dots]$$ を形成できる。最大イデアル $$\mathfrak{m}$$ で局所化すると、局所環 $$T$$ を得る。Hecke代数の最大イデアルは、あるガロア表現（あるいはHecke固有値系）に対応するとみなせる。
2. **普遍変形環** $$R$$:\
   剰余表現 $$\overline{\rho}\colon G_{\mathbb{Q}} \to \mathrm{GL}_2(\overline{\mathbb{F}}_p)$$ が与えられたとき、各素点に対する局所条件（非分岐、半安定、ordinary など）を課して変形を考える。Schlessinger の可表現性基準（変形理論の標準的道具）によって、**普遍変形環 (universal deformation ring)** $$R$$ が存在し、「同じ局所条件下での任意の変形」は一意的に $$R$$ を経由して得られる、という普遍性を満たす。

### **28.2.2 部分同型の構成とパッチング**

1.  **有限段階での同型** $$\;R_n \cong T_n$$:\
    まず各有限段階 $$n$$ ごとに、

    * $$R_n$$: レベル $$n$$ までの局所条件を含む変形環
    * $$T_n$$: レベル $$n$$ 以下のモジュラー形式のHecke代数を局所化したもの\
      を考える。\
      そして、変形環とHecke代数の**接空間 (tangent space)**（コホモロジー的制約を反映）を比較し、局所条件が一致することを確認すると、

    $$
    R_n \;\cong\; T_n
    $$

    という同型が得られる。
2. **各段階間の整合性**:\
   $$n$$ から $$n+1$$ へ上がるとき、$$R_{n+1}$$ はより精密な変形データを表し、$$T_{n+1}$$ はより高いレベルのモジュラー形式をエンコードする。パッチングでは、$$R_{n+1} \to R_n$$ と $$T_{n+1} \to T_n$$ の対応が自然に対応付くことを示す必要がある。
3.  **逆極限**:\
    各段階間の環準同型 $$R_{n+1} \to R_n$$、$$T_{n+1} \to T_n$$ が両立的（compatible）であるため、逆極限で誘導される写像

    $$
    \varprojlim R_n \;\longrightarrow\; \varprojlim T_n
    $$

    を得る。適切な条件（制御定理や局所-大域整合性などで検証できる）を満たすとき、この写像は**同型**となる。さらに、$$\varprojlim R_n$$ と $$R$$、$$\varprojlim T_n$$ と $$T$$ &#x3092;_&#x540C;一&#x8996;_&#x3067;きるので、

    $$
    R \;\cong\; T
    $$

    が結論される。

### **28.2.3 すべての素点における取り扱い**

重要なのは、元の楕円曲線（あるいはガロア表現）が興味深い分岐を起こす素点&#x3092;_&#x3059;べ&#x3066;_&#x304D;ちんと局所条件に組み込むことである、という点です。半安定楕円曲線は有限個の素点で悪い還元をもつ可能性がありますが、そうした素点ごとに局所変形条件を課し、見落としがないようにする必要があります。歴史的にも、ワイルズとテイラーの研究では、各素点での局所変形条件を非常に緻密に設定・処理することで、すべてを抜け漏れなく扱うことに成功しました。

***

## **28.3 帰結：モジュラー楕円曲線とFLT**

### **28.3.1 半安定曲線に対する谷山–志村–Weil予想**

$$R \cong T$$ の証明は、$$\mathbb{Q}$$ 上の特定の楕円曲線が **モジュラー** であることを示すために必要な要点です。実際、半安定楕円曲線 $$E$$ を取り、その剰余表現 $$\overline{\rho}_E$$ に対応するHecke代数 $$\mathbf{T}$$ の最大イデアル $$\mathfrak{m}$$ で局所化するとします。すると、$$R \cong T$$ は

1. $$R$$ でパラメータ化される大域ガロア表現が、Hecke代数 $$T$$ により与えられるモジュラー固有形式から来るガロア表現と**同一**であることを意味する。
2. したがって $$E$$ は（同種 (isogeny) を除いて）重さ2のモジュラー形式と対応し、モジュラー楕円曲線となる。

こうして、半安定楕円曲線に対する谷山–志村–Weil予想、すなわち「$$\mathbb{Q}$$ 上の半安定楕円曲線はすべてモジュラーである」という命題が証明されることになります。これがワイルズの主目的でした。

### **28.3.2 フェルマーの最終定理**

歴史的には、この谷山–志村–Weil予想の動機の一つがフェルマーの最終定理の解決でした。議論はよく知られた **Frey曲線** を用いた論法を経由します。

1. $$x^n + y^n = z^n$$（$$n>2$$）に非自明解があると仮定する。
2. その解 $$(x,y,z)$$ から **Frey曲線** $$E$$ を構成する。するとこの曲線の conductor（伝導度）は $$(x,y,z)$$ によって決まるが、これは半安定となる。
3. 半安定曲線に対する谷山–志村–Weil予想（今や証明済み）より、$$E$$ はモジュラーでなければならない。
4. しかし Ribet のレベル下降 (level-lowering) 定理により、もし $$E$$ がモジュラーならば、あるHecke形式の間にあり得ない合同が起こってしまい、矛盾を導く。\
   （これにより $$(x,y,z)$$ は自明解以外に存在しないことになる。）

よって、$$n>2$$ の場合に非自明解は存在しない、すなわち FLT が成り立つ。

***

## **歴史的・概念的補足**

1. **Mazur の基盤的研究**: Barry Mazur は Iwasawa 理論において先駆的な成果を挙げ、ワイルズのパッチング論法を下支えする「制御定理」の基盤を築きました。
2. **Frey、Serre、Ribet**: Gerhard Frey は、FLT の解決が「ある種の楕円曲線のモジュラー性」を示すことに帰着することを指摘し、Jean-Pierre Serre は $$\mathrm{mod}\,p$$ ガロア表現に関する深遠な予想を提起しました。Ken Ribet はレベル下降定理を証明し、FLT をモジュラー性の問題に直接結びつける端緒を開きました。
3. **ギャップ修正**: ワイルズが最初の証明を発表した際、一部のコホモロジー類の消去に関して微妙な問題が残りました。Richard Taylor との共同研究で、パッチング論法の修正が提案され、最終的な完成に至ります。
4. **半安定を超えて**: Breuil, Conrad, Diamond, Taylor はパッチング論法をさらに拡張し、半安定性の仮定を取り除いて、$$\mathbb{Q}$$ 上の一般の楕円曲線にもモジュラー性を証明するに至りました。

***

## **例示：イメージを掴むために**

### **例 28.1（非分岐表現の局所変形環）**

$$K = \mathbb{Q}_p$$ とする。ある剰余表現 $$\overline{\rho}: G_K \to \mathrm{GL}_2(\overline{\mathbb{F}}_p)$$ &#x304C;_&#x975E;分&#x5C90;_&#x3067;あるとし、その持ち上げ（リフト）$$\mathrm{GL}_2(\overline{\mathbb{Q}}_p)$$ も非分岐であるような変形を**非分岐変形**と呼ぶ。この簡単な場合:

* **非分岐変形の普遍変形環** $$R_{\mathrm{unram}}$$ は、通常、ウィットベクトル環 $$\mathcal{O}$$（$$\overline{\mathbb{F}}_p$$ 上のウィットベクトル）に変数 $$X$$ を付け加えた形式 $$\mathcal{O}[[X]]$$ に対応し、非分岐という条件を反映するような関係式で割った形になる。
* 局所コホモロジー $$\mathrm{H}^1(K,\overline{\rho})$$ の「非分岐部分拡大」の次元が 1 程度になる場合が多く、これが普遍変形環の次元（局所環としての次元）を与える目安になる。

実際には、ordinary 性などを課すとより複雑になるが、こうした局所条件を課して得られる変形環が $$\mathcal{O}[[X]] / (\text{関係式})$$ のような形で記述され、それを素点ごとに組み合わせていくことがパッチングの核心となる。

### **例 28.2（サイクロトミー塔における制御）**

* $$\Gamma = \mathrm{Gal}(\mathbb{Q}(\zeta_{p^\infty})/\mathbb{Q}) \cong \mathbb{Z}_p^\times$$ とする。
* ガロア加群 $$M$$ を考え、$$\Gamma_n$$（$$\Gamma$$ の指数 $$p$$ の部分群）について $$\mathrm{H}^1(\Gamma_n, M)$$ と $$\mathrm{H}^1(\Gamma_{n+1}, M)$$ を比較する。
* **制御定理**は例えば「$$\mathrm{H}^1(\Gamma_{n+1}, M)$$ の $$\dim_{p}$$ は $$\mathrm{H}^1(\Gamma_n, M)$$ のそれとちょうど一定量 $$\delta$$ だけ違う」あるいは「ある段階以降は次元が変化しない」などの形をとり、これは局所・大域コホモロジーの有限次元性を保証する。

このような性質が成り立つことで、各段階のコホモロジー群の逆極限がよく定義され、しかも有限次元として保たれることが示せる。これがパッチングの要件となるわけです。

***

## **結論と今後の展望**

本**第28節**では、ワイルズとテイラーが $$R \cong T$$ を証明するために用いた**パッチング論法**を概説しました。その要点は以下の通りです。

1. 有限段階の変形環とHecke代数を構成する。
2. コホモロジー的な次元比較と局所-大域整合性を用いて、それらが段階ごとに一致 ($$R_n \cong T_n$$) することを示す。
3. 逆極限をとることで、大域的に $$R \cong T$$ が確立される。
4. 結果として、半安定楕円曲線のモジュラー性およびフェルマーの最終定理が証明される。

**次はどこへ？**

* **第29節**では、**Iwasawa 代数**やさらに一般的な**無限拡大**における手法を詳しく見ていきます。FLT のために用いられたケースから、より一般的な理論へ拡張する流れを追います。
* 後の節（30–34）では、より広範な Langlands 計画への応用、セルマー群の構造、そしてパッチングという視点が複数のモジュラリティ・変形の結果をどのように統合しているかを取り上げます。

$$R \cong T$$ の証明スケッチを終えた今、ワイルズのパッチング論法は、局所変形理論・大域コホモロジー・モジュラー形式論の深い結果を巧みに統合した、数論における最も独創的な構成の一つとして位置付けられるでしょう。
