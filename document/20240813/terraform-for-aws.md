# Terraform-for-AWS

## S3

例

1. Bucket の作成

```
resource "aws_s3_bucket" "finance" {
    bucket = "finance-20240813"
    tags = {
        Desription = "Finance and Payroll"
    }
}
```

補足

- bucket 名は一意
- bucket はオプショナルのため、指定しない場合は一意のランダム文字列が付与される

2. ファイルのアップロード

```
resource "aws_s3_bucket_object" "finance-2024" {
    content = "/root/finance/finance-2024.doc"
    key = "finance-2024.doc"
    bucket = aws_s3_bucket.finance.id
}
```

補足

- bucket には、1. で作成したリソースを指定している。

3. IAM グループのデータ

```
data "aws_iam_group" "finance-data" {
    group_name = "finance-analysts"
}
```

4. bucket にポリシーを設定

```
resource "aws_s3_bucket_policy" "finance-policy" {
    bucket = aws_s3_bucket.finance.id
    policy = <<EOF
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Action": "*",
                "Effect": "Allow",
                "Resource": "arn:aws:s3:::${aws_s3_bucket.finance.id}/*",
                "Principal": {
                    "AWS": [
                        "${data.aws_iam_group.finance-data.arn}"
                    ]
                }
            }
        ]
    }
    >>
}
```

補足

- bucket には、1. で作成したリソースを指定している。
- Pricinpal には、3. で作成したデータソースを指定している。
