# Terraform について

- Infrastructure as Code(IaC)の一種
- Iac である CloudFormation は AWS に特化しているが、Terraform は他ベンダーサービスにも使用できる
- HCL 構文（HashiCorp 設定言語）で構成される

## IaC のメリット、オンプレとの違い

- 人的コスト、時間コストが大幅に削減される
- 人為的ミスの可能性が大幅に削減される
- スケールアップ、スケールダウンが簡単

## IaC で使用される主なツール

### Configuration Management

既存のインフラリソースにインストールして管理でき、コードで自動化する

- Ansible
- Puppet
- SaltStack

### サーバーテンプレート化ツール

仮想マシンやコンテナのカスタムイメージを作成する

- Docker
- Packer
- Vagrant

### プロビジョニングツール

多岐に渡るインフラストラクチャ・コンポーネントをプロビジョンングする

- Terraform
- CloudFormation

## コマンド

- init
  - 初期化
- plan
  - 実行計画の確認
- apply
  - デプロイ
