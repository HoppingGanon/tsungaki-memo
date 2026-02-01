# Google OAuth スマホアプリ実装方法

## Question

Google OAuth をスマホアプリで実行する場合、どこにリダイレクトされるか？外部ブラウザ、内部、WebView、その他の方法は？Cognitoが抽象化してくれるか？

## Answer

**推奨: In-App Browser（ASWebAuthenticationSession / Chrome Custom Tabs）**

| 方式 | 推奨度 | 備考 |
|------|--------|------|
| In-App Browser | ✅ 推奨 | iOS: ASWebAuthenticationSession、Android: Chrome Custom Tabs |
| 外部ブラウザ | △ | UXが悪い（アプリ外に出る） |
| WebView | ❌ | **Googleが禁止** |

## 補足

### 実装構成

```
Capacitor + AWS Amplify Auth
  → federatedSignIn({ provider: 'Google' })
  → In-App Browser で認証
  → カスタムURLスキーム (myapp://) でアプリに戻る
  → Cognito トークン取得
```

### Cognito の抽象化

AWS Amplify SDK を使えば、Cognitoがプラットフォーム差異を吸収。Web/iOS/Android で同一コードで動作可能。
