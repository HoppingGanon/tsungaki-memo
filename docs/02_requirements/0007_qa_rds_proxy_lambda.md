# RDS Proxy と Lambda + RDS 接続

## Q
Lambda から PostgreSQL に接続する場合、RDS Proxy が必須か？ECS構成でも必要か？

## A
- **Lambda → RDS**: RDS Proxy 推奨（接続数爆発リスク）
- **ECS/EC2 → RDS**: 通常不要（アプリ側でコネクションプール管理）

## 補足
- Lambda 同時実行で DB 接続数が急増し max_connections 超過のリスクあり
- RDS Proxy のコストは約 $15〜30/月

## 結論
RDS Proxy のコスト増を避けるため、**Lambda + DynamoDB を継続**。
