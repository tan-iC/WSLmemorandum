
# WSL memorandum

## Theme

- Powershellを使ってコマンドのみでWSL環境構築
- なんも知らなくてもHelloWorldできるようになる

## Environment

Windows10 / Windows11

## Setup

### Install

1. `Powershell`を「管理者として実行」

    ![Test Image 1](img/install01.PNG "cap1")

1. `wsl -l -o`で利用可能なディストリビューション一覧を表示

    ![Test Image 2](img/install02.PNG "cap2")

1. `wsl --install -d {$distribution}`で`$distribution`をインストール

    ```powershell
    # 例 : Ubuntu 18.04 LTSをインストール
    wsl --install -d Ubuntu-18.04
    ```

    ![Test Image 3](img/install03.PNG "cap3")

1. PCを再起動

    ![Test Image 4](img/install04.PNG "cap4")

### Setting

あとは普通のLinux distributionsの扱い

1. usernameを入力
1. passwordを入力 (`passwd`コマンドで再設定可能)
1. 必要なパッケージの取得 (任意)
    1. `sudo apt update`
    1. `sudo apt upgrade -y`
    1. `sudo apt install build-essential -y`
    1. HelloWorldへ

### VSCode

1. アドオン`Remote Development`をインストール

    ![Test Image 5](img/vscode01.PNG "cap5")

1. 画面左下緑のボタンから「WSLでフォルダを開く」ことが可能

    ![Test Image 6](img/vscode02.PNG "cap6")

## Network

うまくネットワークに接続できないとき

1. DNSに問題がある場合

    ```bash
    sudo rm /etc/resolv.conf
    sudo sh -c "echo 'nameserver 8.8.8.8' > /etc/resolv.conf"
    ```

    [こちら](https://qiita.com/kkato233/items/1fc71bde5a6d94f1b982)より

    wslでは`/etc/resolv.conf`が自動生成され、nameserverが設定されるが、この設定が良くない場合がある(?)

1. セキュリティソフトに問題がある場合

    基本的にファイアウォールの設定が必要

    1. [McAfee-1](https://kcm.trellix.com/corporate/index?page=content&id=KB94601)
    1. [Symantec-1](https://teratail.com/questions/59081)
    1. [Symantec-2](https://kemasoft.net/?vm/wsl2%A4%C8SEP%A4%C8stone)
    1. [Symantec-3](https://jpdebug.com/p/2820485)

### Proxy

## SSH (Git/GitHub)

## Downgrade to WSL1

1. [こちら](https://yoshinorin.net/articles/2020/08/22/downgrade-wsl2-to-wsl1/)より

    ```powershell
    wsl --set-version {$distribution} 1
    ```

## Reference

1. <https://learn.microsoft.com/ja-jp/windows/wsl/install#manual-installation-steps>

1. <https://qiita.com/yo_kanyukari/items/37421f497b7ffaa75502>

1. <https://qiita.com/2019Shun/items/5ab290a4117a00e373b6>

1. <https://qiita.com/kkato233/items/1fc71bde5a6d94f1b982>

1. <>
