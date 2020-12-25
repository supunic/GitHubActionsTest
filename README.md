# GitHub Actions

## Hello, World
```yml
name: Hello, World! # ワークフローの名前
on: push # リポジトリpushイベント時に実行するよう定義

jobs: # ワークフロー内で実行されるジョブを定義
  build: # ジョブのid（ユニークであれば何でも可）
    name: Greeting # ジョブ名
    runs-on: ubuntu-latest # ジョブが実行される仮想環境を指定
    steps: # ジョブ内で実行される処理の定義
      - run: echo "Hello, World!"
```

## 機能

### ワークフロー

#### 内容
**ワークフロー**
- リポジトリ内のソフトウェア開発における何かしらのプロセスを自動化したもの
  - ソフトウェアのbuild, test, packaging, deployなど
  - push時だけでなく、issueやプルリク時に設定できる
- 1つ以上のジョブから構成される
- 並列実行も、順次実行も可能

**ジョブ**
- ワークフローを構成するタスク実行単位
- 複数のステップから構成される

**ステップ**
- ジョブを構成するアクションやコマンド実行を行う単位

**アクション**
- ステップの中で呼び出される何かしらの処理の塊を表す単位
- コミュニティで共有されているものを利用できる
- 自作も可能

#### 保存場所
- 設定ファイルは`.github/workflows`直下に保存する
- `.yml`拡張子でかく
- 複数作成可能

**ディレクトリ構造例**
```
(repositoryroot)
|-- .github
|   `-- workflows
|       |-- continuousdelivery.yml
|       |-- issuemanagement.yml
|       ...
...
```

