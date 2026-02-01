# DynamoDB vs PostgreSQL（Lambda用データストア）

## Q
DynamoDBの用途がPush通知の送信対象読み取りだけなら、PostgreSQLやQdrantで代替できるか？

## A
**技術的には可能だが、Lambda + PostgreSQL は RDS Proxy が必要になる問題がある。** Qdrant は単一キー検索に最適化されておらず非推奨。

## 結論
この議論は RDS Proxy 検討を経て、最終的に **Lambda + DynamoDB を継続** する方針となった。
