# Variables

ハードコーディングしていた値を変数とすることによって再利用性が高まる

## 定義

- `variable`をというキーワードを使用する。この後に変数名が続く
- 使用する側は変数名の前に`var`を付与する
- 更新は更新したい箇所を修正するだけで良い
- default = 変数の中身
  - オプショナルのため、指定しないと他の方法で指定することになる
    - 環境変数
    - tfvars ファイル
    - terraform apply 時に指定
- description = 変数の説明
- type = 変数の型
  - 指定しない場合は、any 型となる
  - string,number,bool,any,list,map,object,taple

main.tf

```
resource "local_file" "pet" {
    filename = var.filename
    content = var.content
}
```

variables.tf

```
variable "filename" {
    default = "root/pet.txt"
    description = "faile path"
    type = string
}

variable "content" {
    default = "we love pets"
}
```
