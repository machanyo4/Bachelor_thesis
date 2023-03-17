# Bachelor_thesis

福井大学工学部　理と匠の研究室　B4 での卒論研究で用いたファイルを格納したフォルダ

Title: "Coordinate proposal method based on deep learning", "深層学習を用いたコーディネート提案手法"

本フォルダ内(Bachelor_thesis)のファイルツリー構造は以下のようである. 

<pre>
.
├── NN
│   ├── NN0_output.ipynb
│   ├── NN1_output.ipynb
│   ├── NN2_output.ipynb
│   ├── NN3_output.ipynb
│   ├── NN4_output.ipynb
│   ├── NNtest0.ipynb
│   ├── NNtest1.ipynb
│   ├── NNtest2.ipynb
│   ├── NNtest3.ipynb
│   ├── NNtest4.ipynb
│   ├── nn0_apply.pt
│   ├── nn1_apply.pt
│   ├── nn2_apply.pt
│   ├── nn3_apply.pt
│   └── nn4_apply.pt
├── RBMForBinData
│   ├── RBM_for_bindata_apply.ipynb
│   ├── output_RBM_apply.ipynb
│   └── rbm_apply.pt
└── dataset
    ├── combine-data.gsheet
    ├── make_pickle_dataset.ipynb
    └── pic.bin
</pre>


# DEMO

FNN を用いたトップスデータに対するボトムスの評価値の出力結果

|隠れノードの数| 平均二乗誤差 | 誤差の最大値 | 汎化指標 |
|------------|------------|-------------|--------|
|     32     |    0.0389   |  	0.18    |  0.814 |
|     64     |    0.0174   |    0.14    |  0.481 |
|    128     |    0.0095   |    0.12    |  0.634 |
|    256     |    0.0083   |    0.12    |  0.662 |
|    512     |    0.0039   |    0.12    |  0.675 |

RBM が出力したデータがテストデータと完全一致した割合 0%

訓練データと同じであるトップスの種類を表すバイアス値と所属している色相環の 12 のグループの両方の一致率は 80%

このとき, ボトムスの評価値も一致していた割合は 66%

# Requirement

本プログラムは Google Colaboratory を用いて実装することを前提としている. 必要なライブラリは各プログラムファイルにて記載済み.

# Elements

./dataset &rarr; 本研究で用いるデータを格納. 

<pre>
/combine-data.gsheet &rarr; トップスデータとそれに対するボトムスの評価値を与えた組み合わせデータ.

/make_pickle_dataset.ipynb &rarr; gsheet に記載されたデータの整形, データセットの作成を行い pickle ファイルに保存するプログラム.

/pic.bin &rarr; make_pickle_dataset.ipynb 実行時に生成される pickle ファイル. 機械学習に用いるデータセット. 
</pre>

./RBMForBinData &rarr; RBM に関するファイルを格納.

<pre>
/RBM_for_bindata_apply.ipynb &rarr; 二値 (0 or 1) を扱う可視層および隠れ層の 2 層からなる RBM モデル. 実行終了時に学習したパラメータを保存. 

/rbm_apply.pt &rarr; 学習済みの RBM のパラメータが保存されたファイル. 

/output_RBM_apply.ipynb &rarr; 保存した RBM のパラメータを用いて推論を行うプログラム. 
</pre>

./NN &rarr; FNN に関するファイルを格納. 

<pre>
/NNtest*.ipynb (* は 0 ~ 4)  &rarr; 1 層の中間層 を持つ FNN モデル. 実行終了時に学習したパラメータを保存. 

/nn*_apply.pt (* は 0 ~ 4) &rarr; 学習済みの FNN のパラメータが保存されたファイル. 

/NN*_output.ipynb (* は 0 ~ 4) &rarr; 保存した FNN のパラメータを用いて推論を行うプログラム. 
</pre>

\* の数字と中間層のノード数の関係は以下の表のようである. 

|* の数字|中間層のノード数|
|-------|-------------|
|   0   |     32      |
|   1   |     64      |
|   2   |     128     |
|   3   |     256     |
|   4   |     512     |

# Usage

本フォルダの大まかな活用方法

1. Google Drive の MyDrive 直下に Bachelor_thesis フォルダを作成.
2. Bachelor_thesis　中に全てのフォルダを格納
3. Elements で説明したファイルの順番に実行. 

# Note

細かな説明はプログラムファイルに記載. 
不明な点は Author まで. 

# Author

福井大学工学部　理と匠の研究室　松原佳寛
