# DynamoDB を AWS 実環境のみで使用

## Q
DynamoDB は開発後半でしか使わず、費用も安いので、LocalStack から外して AWS 実環境のみで使用しては？

## A
**採用。** DynamoDB の無料枠（25 RCU/WCU、25GB）でリマインダー通知程度なら十分収まる。

## 結論
**DynamoDB も Cognito と同様に、全環境で AWS 実環境を使用。**
