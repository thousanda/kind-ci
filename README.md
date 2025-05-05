# kind CI
## 概要
CIでKubernetesマニフェストの妥当性を検証するためのコンセプトを紹介するリポジトリです。

kindでKubernetesクラスターを作成し、そこでdry-runを試すことで、マニフェストに問題がないか確認できます。

kindはKubernetes in Dockerの略で、ローカルで軽量なKubernetesクラスターを立ち上げるためのツールです。コンテナでnodeを構成するため、このような名前になっています。

## ディレクトリ構成
### CI
#### GitHub Actions
```
.github
└── workflows
    └── validate-manifest.yml
```
CIで実行する内容が定義されています。

1. kindをインストールする
1. kubectlをインストールする
1. kindクラスターを作成する
1. dry runを試す

#### CI用のconfig
```
ci
└── kind-config.yaml
```
kindクラスターを作る時に使う設定ファイルです。

### Manifest
```
manifest
└── pod.yaml
```
検証の対象となるマニフェストの例です。
