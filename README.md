# Yolks

PterodactylのEggシステムで使用できるコアイメージの厳選されたコレクションです。各イメージは、依存関係が常に最新の状態であることを保証するために定期的に再構築されます。

イメージは `ghcr.io` にホストされており、`games`、`installers`、および `yolks` スペースの下に存在します。各イメージの配置場所を決定する際には、次のロジックが使用されます。

* `oses` — 基本的なパッケージを含むベースイメージで、スタートのためのコアパッケージが含まれています。
* `games` — リポジトリ内の `games` フォルダ内にあるもの。特定のゲームやゲームタイプを実行するために作成されたイメージです。
* `installers` — `installers` ディレクトリ内にあるもの。これらのイメージは、Pterodactylの異なるEggsのインストールスクリプトで使用され、実際にゲームサーバーを実行するためのものではありません。これらのイメージは、一般的なインストールの依存関係（`curl`や`wget`など）を事前にインストールすることで、インストール時間とネットワーク使用量を削減するために設計されています。
* `yolks` — さまざまな種類のゲームやスクリプトを実行できる、より一般的なイメージです。通常は特定のソフトウェアのバージョンであり、Pterodactyl内の異なるEggsが基盤の実装を切り替えることを可能にします。例えば、JavaやPythonのようなものは、ボットやMinecraftサーバーを実行するために使用されます。

これらのイメージは特に指定がない限り、すべて `linux/amd64` および `linux/arm64` バージョンで利用可能です。arm64システムでこれらのイメージを使用する場合、イメージやタグの変更は不要で、そのまま動作します。

## 貢献方法

既存のイメージに新しいバージョン（例: `java v42`）を追加する場合、そのバージョンの子フォルダ（例: `java/42/Dockerfile`）内に追加します。また、新しいバージョンが正しくタグ付けされるように、該当する `.github/workflows` ファイルも更新してください。

## 利用可能なイメージ

* [`ベース OS`](https://github.com/pterodactyl/yolks/tree/master/oses)
  * [`alpine`](https://github.com/pterodactyl/yolks/tree/master/oses/alpine)
    * `ghcr.io/pterodactyl/yolks:alpine`
  * [`debian`](https://github.com/pterodactyl/yolks/tree/master/oses/debian)
    * `ghcr.io/pterodactyl/yolks:debian`
* [`ゲーム`](https://github.com/pterodactyl/yolks/tree/master/games)
  * [`rust`](https://github.com/pterodactyl/yolks/tree/master/games/rust)
    * `ghcr.io/pterodactyl/games:rust`
  * [`source`](https://github.com/pterodactyl/yolks/tree/master/games/source)
    * `ghcr.io/pterodactyl/games:source`
* [`golang`](https://github.com/pterodactyl/yolks/tree/master/go)
  * [`go1.14`](https://github.com/pterodactyl/yolks/tree/master/go/1.14)
    * `ghcr.io/pterodactyl/yolks:go_1.14`
  * [`go1.15`](https://github.com/pterodactyl/yolks/tree/master/go/1.15)
    * `ghcr.io/pterodactyl/yolks:go_1.15`
  * [`go1.16`](https://github.com/pterodactyl/yolks/tree/master/go/1.16)
    * `ghcr.io/pterodactyl/yolks:go_1.16`
  * [`go1.17`](https://github.com/pterodactyl/yolks/tree/master/go/1.17)
    * `ghcr.io/pterodactyl/yolks:go_1.17`
* [`java`](https://github.com/pterodactyl/yolks/tree/master/java)
  * [`java8`](https://github.com/pterodactyl/yolks/tree/master/java/8)
    * `ghcr.io/pterodactyl/yolks:java_8`
  * [`java8 - OpenJ9`](https://github.com/pterodactyl/yolks/tree/master/java/8j9)
    * `ghcr.io/pterodactyl/yolks:java_8j9`
  * [`java11`](https://github.com/pterodactyl/yolks/tree/master/java/11)
    * `ghcr.io/pterodactyl/yolks:java_11`
  * [`java11 - OpenJ9`](https://github.com/pterodactyl/yolks/tree/master/java/11j9)
    * `ghcr.io/pterodactyl/yolks:java_11j9`
  * [`java16`](https://github.com/pterodactyl/yolks/tree/master/java/16)
    * `ghcr.io/pterodactyl/yolks:java_16`
  * [`java16 - OpenJ9`](https://github.com/pterodactyl/yolks/tree/master/java/16j9)
    * `ghcr.io/pterodactyl/yolks:java_16j9`
  * [`java17`](https://github.com/pterodactyl/yolks/tree/master/java/17)
    * `ghcr.io/pterodactyl/yolks:java_17`
  * [`java17 - OpenJ9`](https://github.com/pterodactyl/yolks/tree/master/java/17j9)
    * `ghcr.io/pterodactyl/yolks:java_17j9`
  * [`java18`](https://github.com/pterodactyl/yolks/tree/master/java/18)
    * `ghcr.io/pterodactyl/yolks:java_18`
  * [`java18 - OpenJ9`](https://github.com/pterodactyl/yolks/tree/master/java/18j9)
    * `ghcr.io/pterodactyl/yolks:java_18j9`
  * [`java19`](https://github.com/pterodactyl/yolks/tree/master/java/19)
    * `ghcr.io/pterodactyl/yolks:java_19`
  * [`java19 - OpenJ9`](https://github.com/pterodactyl/yolks/tree/master/java/19j9)
    * `ghcr.io/pterodactyl/yolks:java_19j9`
  * [`java21`](https://github.com/pterodactyl/yolks/tree/master/java/21)
    * `ghcr.io/pterodactyl/yolks:java_21`
* [`nodejs`](https://github.com/pterodactyl/yolks/tree/master/nodejs)
  * [`node12`](https://github.com/pterodactyl/yolks/tree/master/nodejs/12)
    * `ghcr.io/pterodactyl/yolks:nodejs_12`
  * [`node14`](https://github.com/pterodactyl/yolks/tree/master/nodejs/14)
    * `ghcr.io/pterodactyl/yolks:nodejs_14`
  * [`node15`](https://github.com/pterodactyl/yolks/tree/master/nodejs/15)
    * `ghcr.io/pterodactyl/yolks:nodejs_15`
  * [`node16`](https://github.com/pterodactyl/yolks/tree/master/nodejs/16)
    * `ghcr.io/pterodactyl/yolks:nodejs_16`
  * [`node17`](https://github.com/pterodactyl/yolks/tree/master/nodejs/17)
    * `ghcr.io/pterodactyl/yolks:nodejs_17`
  * [`node18`](https://github.com/pterodactyl/yolks/tree/master/nodejs/18)
    * `ghcr.io/pterodactyl/yolks:nodejs_18`
  * [`node20`](https://github.com/pterodactyl/yolks/tree/master/nodejs/18)
    * `ghcr.io/pterodactyl/yolks:nodejs_20`
* [`python`](https://github.com/pterodactyl/yolks/tree/master/python)
  * [`python3.

7`](https://github.com/pterodactyl/yolks/tree/master/python/3.7)
    * `ghcr.io/pterodactyl/yolks:python_3.7`
  * [`python3.8`](https://github.com/pterodactyl/yolks/tree/master/python/3.8)
    * `ghcr.io/pterodactyl/yolks:python_3.8`
  * [`python3.9`](https://github.com/pterodactyl/yolks/tree/master/python/3.9)
    * `ghcr.io/pterodactyl/yolks:python_3.9`
  * [`python3.10`](https://github.com/pterodactyl/yolks/tree/master/python/3.10)
    * `ghcr.io/pterodactyl/yolks:python_3.10`

### インストールイメージ

* [`alpine-install`](https://github.com/pterodactyl/yolks/tree/master/installers/alpine)
  * `ghcr.io/pterodactyl/installers:alpine`

* [`debian-install`](https://github.com/pterodactyl/yolks/tree/master/installers/debian)
  * `ghcr.io/pterodactyl/installers:debian`
