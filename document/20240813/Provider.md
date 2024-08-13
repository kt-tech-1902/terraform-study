# Provider

## Provider の種類

1. 公式プロバイダー
   1. HashiCorp によって配布。Terraform レジストリで一般公開している
   2. AWS,GCP,Azure といった主要なクラウドプロバイダーを含む
2. パートナープロバイダー
   1. HashiCorp のサードパーティ企業によって所有・管理
   2. bigip,Heroku,DigitalOcean など
3. コミュニティプロバイダー
   1. HashiCorp コミュニティに所属している個々が管理
   2. activedirectory,ucloud,netapp-gcp など

## init 実行時の Provider 確認

### 構成

構成:{ホスト名}/{組織名}/{ProviderType}
例　:registory.terraform.io/hashicorp/local

補足

- ProviderType は AWS,AzureRM,Google,Random などがある
- ホスト名は省略される場合がある

## 複数 Provider
