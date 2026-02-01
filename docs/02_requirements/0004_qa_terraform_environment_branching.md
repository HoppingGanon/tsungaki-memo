# Terraformでの環境分岐

## Q
開発環境と本番環境で構成が異なる場合、Terraformで複雑な分岐は書けるか？

## A
**可能。** `count`/`for_each` による条件付きリソース作成、Providerエイリアスによる LocalStack/AWS 切替、環境別 tfvars で対応できる。

## 補足
- `count = var.use_localstack ? 0 : 1` でリソース作成をスキップ可能
- Provider を `aws.localstack` / `aws.real` で切り替え可能
- `terraform apply -var-file="dev.tfvars"` で環境別に実行
