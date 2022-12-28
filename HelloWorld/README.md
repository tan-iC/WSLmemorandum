
# HelloWorld

## C

1. `gcc`は``によりインストール済み

1. [src](src/c "src1")をコンパイル・実行

    ```bash
    ```

## C++

1. `g++`は``によりインストール済み

1. [src](src/cpp "src2")をコンパイル・実行

    ```bash
    ```

## Python

1. `Python3`のインストール

    ```bash
    ```

1. [src](src/py "src3")を実行

    ```bash
    ```

## LaTeX

### 1.`texlive`のインストール (古いものの可能性があるので`apt`は使わない)

- リソースを取得

```bash
curl -OL http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz
tar xvf install-tl-unx.tar.gz
cd install-tl-2*
sudo ./install-tl -no-gui -repository http://mirror.ctan.org/systems/texlive/tlnet/
```

- インストールのオプションを聞かれる -> `I`を入力
- インストール開始

```bash
I
```

- `tlmgr`のパスを通す

```bash
sudo /usr/local/texlive/2022/bin/x86_64-linux/tlmgr path add
```

- アップデート

```bash
sudo tlmgr update --self --all
```

### 2.VScode側のセッティング

- 拡張機能`LaTeX Workshop`をインストール

- `.latexmkrc`によるビルドを可能にする

```bash
```

- ショートカットキーの設定

### 3.サンプルのビルド

- `ctrl+Alt+b`

## 参考文献

1. <https://zenn.dev/minatoneko/articles/b4038eb6524199>
1. <https://texwiki.texjp.org/?Linux#texlive>
1. <>
