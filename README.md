### 2章

### 3章

### 4章 GLMのモデル選択
#### ストーリー
* GLMでは1つのデータを説明する複数のモデルが考えられる
* モデルを選択する基準としてAICを考える

#### 結論
* モデルの選択には最大対数尤度ではなく平均対数尤度で判定するべきである
* 上記はAICで判定するべきと言いかえることもできる
* モデル選択の目的は**真のモデル**を求めることではない

#### メモ
* 平均対数尤度は（真のモデルは一般的には不明なため）直接計算で求めることはできない
* 平均対数尤度の**推定量**は**最大対数尤度 - モデルのパラメータ数**で与えられる
* (最大対数尤度は過大評価されているのでその補正を入れる必要があるらしい)
* 尤度が最大になるモデルは**データ数とパラメータ数が等しいfullmodel**の場合

#### 用語の整理
* **最大対数尤度**：モデルの推定に用いる尺度。モデルが既知データに対してどの程度フィットできるか
* **平均対数尤度**：モデルの予測に用いる尺度。モデルが未知データに対してどの程度フィットできるか
* **バイアス**：最大対数尤度から平均対数尤度を減算した値。バイアスは正負いずれの値も取りうる
* **AIC（赤池情報量基準）**：平均対数尤度の推定量に(-2)を乗じた値

### 5章 GLMの尤度比検定と検定の非対称性

#### ストーリー
* 4章ではモデル選択の基準として**AICによるモデル選択**を考えた
* 5章ではモデル選択のもう1つの基準として**Neyman-Personによる検定の枠組み**を考える
* 一定モデルを帰無仮説、xモデルを対立仮説として上の枠組みにおいて扱う
* P値の評価としてPB法とχ2乗分布を用いる

#### 用語の整理
帰無仮説を棄却することで対立仮説採用の根拠とする
* **帰無仮説**：証明したい仮説と対立する仮設
* **対立仮説**：証明したい仮説
* **P値**：帰無仮説が正しいとした場合に観察結果（検定統計量）が生じる確率
* **第1種の過誤**：正しい帰無仮説を誤って棄却すること。**P値が有意水準を超えたら第1種の過誤は回避できると想定**する
* **第2種の過誤**：間違った帰無仮説を誤って棄却しないこと
* **PB法**：
* **χ2乗検定**：
* **検定統計量**：サンプルデータから計算する変数。帰無仮説が成立した場合に期待される値との比較に利用する

#### 注意
* **帰無仮説が棄却されなかった⇛帰無仮説が立証された**ではない
* 「P値が有意水準を超えた場合」と「超えない場合」で結論できることが異なる（=非対称性が存在する）
* AICによるモデル選択は**良いモデルを選ぶ**のが目的
* Neyman-Pearsonの枠組みでは**有意差を検証することを通じて帰無仮説を安全に棄却する**のが目的

### 6章 GLMの応用範囲を広げる

#### ストーリー
* これまではGLMにおいてポアソン分布のみを扱った
* ポアソン分布以外の分布として二項分布およびガンマ分布をGLMにて扱う

### 7章　一般化線形混合モデル（GLMM）

#### ストーリー
* データの取得方法が反復と疑似反復のどちらかを考える
* 反復ならばGLMを疑似反復ならばGLMMを用いる
* 平均と分散が独立している正規分布やガンマ分布では過分散かどうかは確認できない
