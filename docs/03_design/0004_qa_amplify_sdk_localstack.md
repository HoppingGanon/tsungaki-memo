# AWS Amplify SDK と LocalStack

## Question

AWS Amplify SDKを使用する場合、LocalStackで代用可能か？AWS上に構築が必要か？SDKなので構築は不要か？

## Answer

| 項目 | 回答 |
|------|------|
| Amplify SDK の構築 | ❌ 不要（npmパッケージ） |
| Cognito の LocalStack 代用 | ❌ 不可（Google SSO必須のため） |
| AWS 実環境への構築 | ✅ Cognito のみ必要 |

**現在の要件定義書の方針（CognitoのみAWS実環境）で問題なし。**

## 補足

### Amplify SDK とは

クライアントサイドのライブラリ。接続先のエンドポイントを設定で切り替え可能。

### LocalStack と Cognito

| 機能 | LocalStack Community | AWS実環境 |
|------|---------------------|-----------|
| ユーザープール基本操作 | ⚠️ 一部 | ✅ |
| Google SSO | ❌ | ✅ |
| OAuth 2.0 PKCE | ❌ | ✅ |

Google SSOを使う場合、LocalStackでは実質不可能。
