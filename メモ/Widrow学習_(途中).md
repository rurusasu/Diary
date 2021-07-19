# Widrow学習

## 性能学習
Widrow学習は**性能学習** (performance learning) のカテゴリーに属する, 学習則の一つである. このカテゴリーの学習則は, ある特定の性能評価尺度関数 (**コスト関数**(cost function)) を最小化または最大化する重みの集合を見つける様に働く. 

## Widrow学習の学習目標
学習目標は, 非常に単純な型の処理要素に対し, 最小2乗誤差性能関数評価において, 可能な限り最良の重みベクトルを見つけることである. 

## Widrow学習の特徴
Widrow学習は, ニューロコンピューティングでは最も強力な学習則の1つといえる. それは, それがどんな出発点からでも最適な重みベクトルに収束するからである. 

## 最小平均2乗誤差目標
固定確率密度関数 $\rho$に従い ${\bf R}^2$ から取り出された ${\bf x}$ ベクトルの系列 ${\bf x}_1, {\bf x}_2, {\bf x}_3, \cdots$ を考えると, 目標は, 平均2乗誤差
$$
F({\bf w}) \equiv \lim_{N \rightarrow \infin} \frac{1}{N} \sum_{k=1}^N (y_k - y'_k)^2
$$
を最小化する ${\bf w}$ を見つけることである. ここで $y_k$ は入力ベクトル ${\bf x}_k$ に対する処理過程またはシステムの出力であり, $y'_k = {\bf w} \cdot {\bf x}_k$ はそのベクトルに対するADALINEの出力である. 

ここで問題にしていることは, 近似結果が良くなろうと悪くなろうと, $F({\bf w})$を最小化するのに**最も良い仕事**をする ${\bf w}$ ベクトルを見つけたいということである. 

# Widrow学習の導出
Widrow学習を導くために, $F({\bf w})$ の式を以下のように展開する. 
$$
F({\bf w}) = E \left[(y_k - y'_k)^2 \right] \\
= E \left[(y_k - {\bf w}^T {\bf x}_k)^2 \right] \\
= E \left[y_k^2 - 2y_k{\bf w}^T {\bf x}_k + {\bf w}^T {\bf x}_k {\bf x}_k^T {\bf w} \right] \\
= E \left[y_k^2 \right] - 2{\bf w}^T \left[y_k {\bf x}_k \right] + {\bf w}^T E \left[{\bf x}_k {\bf x}_k^T \right] {\bf w} \\
= p -2{\bf w}^T q + {\bf w}^T R {\bf w}
$$

