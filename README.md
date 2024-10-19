# 概要
JJUG CCC 2024 Fall のハンズオンセッション参加者向け資料です

JJUG CCC 2024 Fall  
https://ccc2024fall.java-users.jp

## 目次

- [Part 1：Launch Multi-File Source-Code Programs](https://github.com/java-women/jjug-ccc-2024-fall-hands-on-for-participants/blob/main/part1.md)
- [Part 2：JShell, var & Text Blocks](https://github.com/java-women/jjug-ccc-2024-fall-hands-on-for-participants/blob/main/part2.md)
- [Part 3：Records & Switch](https://github.com/java-women/jjug-ccc-2024-fall-hands-on-for-participants/blob/main/part3.md)

# 事前準備
カンファレンス当日は参加者向けにwifiの用意がないため、事前準備をお願いします
- 本リポジトリをダウンロードし、オフラインで参照できる状態にしておく
- 当日使用するPCにJava 23をインストールする

## Java 23のインストール方法

バージョンさえ合っていれば、ディストリビューション（≒JDKの開発元）は問いません

先にインストールが完了していることの確認方法を説明します  
コマンドプロンプトやターミナルで次のコマンドを実行し、バージョンがJava 23になっていれば完了です

```shell
$ java --version

openjdk 23 2024-09-17
OpenJDK Runtime Environment (build 23+37-2369)
OpenJDK 64-Bit Server VM (build 23+37-2369, mixed mode, sharing)
```

これ以降、環境に応じたインストール方法を紹介します。いずれかを実施した後、上記のとおり確認を済ませてください

### コマンドラインでインストール

[SDKMan](https://sdkman.io/)や[Homebrew](https://brew.sh/)などを使い慣れている方はそちらでJava 23をインストールしてください

### パッケージインストール Windows

- [JDK Development Kit 23 downloads](https://www.oracle.com/java/technologies/downloads/#jdk23-windows)ページを開く
- `x64 Installer`（.exeファイル）をダウンロードする
- ダウンロードしたファイルから `jdk-23_windows-x64_bin.exe` を起動する
- インストーラーの指示に従ってインストールを済ませる

### パッケージインストール Mac

- [JDK Development Kit 23 downloads](https://www.oracle.com/java/technologies/downloads/#jdk23-mac)ページを開く
- お使いの端末にあわせて `DMG Installer`（.dmgファイル）をダウンロードする
- ダウンロードしたファイルから `JDK 23.pkg` を起動する
- インストーラーの指示に従ってインストールを済ませる
