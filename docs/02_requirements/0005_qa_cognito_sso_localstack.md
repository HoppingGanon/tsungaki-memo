# Cognito SSO と LocalStack

## Q1
LocalStack CognitoではSSOの確認ができないのか？cognito-localならカバーできるか？

## A1
**LocalStack / cognito-local ともにSSO検証は不可。** OAuth 2.0/OIDC、Hosted UI、外部IdP連携はサポートされていない。

## Q2
Cognitoは低コストなので、AWS実環境を使用しても良いのでは？

## A2
**推奨。** Cognito は 50,000 MAU まで無料。開発規模なら無料枠内で収まる。

## 結論
**Cognito は全環境（development/vps/production）で AWS 実環境を使用。** cognito-local は使用しない。
