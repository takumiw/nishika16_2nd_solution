# Nishika16 2nd place solution
- [Nishika リチウムイオン電池の充電率予測コンペ](https://www.nishika.com/competitions/16/summary) の最終submissionコードです。
- 解法自体はこちらのディスカッションに記載しています。


# Directory Layout
```
.
├── input                    : Input files
│    ├── train
│    │    ├── n10degC_Cycle_1_Pan18650PF.csv
│    │    ├── ...
│    │    └── p25degC_US06_Pan18650PF.csv
│    ├── test.csv
│    └── sample_submission.csv
├── preprocess.ipynb          : Preprocessing
├── final_submission.ipynb    : Training and Inference
├── poetry.lock 
├── pyproject.toml 
└── README.md
```


# Requirements
下記の環境で動作確認済みです。
- Python 3.7.1
- macOS Big Sur

利用したパッケージは以下の通りです。 (pyproject.tomlにも記載してあります)
- numpy = "^1.20.3"
- pandas = "^1.2.4"
- matplotlib = "^3.4.2"
- seaborn = "^0.11.1"
- scikit-learn = "^0.24.2"


# How to Run
## データのダウンロード
1. https://www.nishika.com/competitions/16/data からコンペのデータをダウンロードし、上記のようにinputディレクトリに展開してください。

2. 下記のいずれかの方法で必要なパッケージをインストールしてください。

```
# Poetryがインストール済みの場合
$ poetry install

# pipで インストールする場合
$ pip install -r requirements.txt
```


## 前処理
`preprocess.ipynb` を上から順に実行してください。前処理後のpickleファイルが input/preprocessed ディレクトリに作成され、学習時に利用するjsonファイルがconfigs ディレクトリに作成されます。


## 学習、推論、submissionファイルの作成
`preprocess.ipynb` を上から順に実行してください。学習を行なった後、submission.csv ファイルが作成されます。


## (参考) Jupyter Notebookの起動
例として、下記の方法で起動できます。
```
# Poetryでパッケージのインストーをした場合
$ poetry run jupyter notebook

# pipでパッケージのインストールをした場合
$ jupyter notebook
```