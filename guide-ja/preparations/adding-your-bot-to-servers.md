# ボットをサーバーに追加する

ここまで熱心に読んできたのなら、ボットのセットアップを終えているでしょう。 しかし、まだサーバーにボットはいません。 これはどうすればいいのでしょうか？

ボットをサーバーに追加するには、ボットアプリケーションのClient IDを使用して作成できる特別な招待リンクを使用してボットを追加する必要があります。

## ボットの招待リンク

この招待リンクは次のような形になります。

```
https://discordapp.com/oauth2/authorize?client_id=123456789012345678&scope=bot
```

このURLの構造は非常にシンプルになっています。

* 最初の部分は、Discordサーバーへに対して追加するOAuth2アプリケーション（ボットアプリケーションなど）を承認するためのDiscordの標準形式です。
* 次の`client_id=...`から始まる部分は認可_したい_アプリケーションを指定します。 有効な招待リンクを作るには、この部分を実際のボットのClient IDに置き換える必要があります。
* 最後の`scope=bot`から始まる部分は、アプリケーションをボットとして追加しようとしていることを示します。

::: tip
`permissions`パラメータでは、追加したサーバーでボットが持つ権限を指定できます。 [この](https://discordapi.com/permissions.html)サイトを使うことで簡単に招待リンクを作れます。
:::

::: warning
もし"Bot requires a code grant"といったエラーが出た場合、ボットのアプリケーション設定を開き、"Require OAuth2 Code Grant"オプションをオフにしてください。 あなたがこれの必要性をよく分かっていない場合はオンにする必要はありません。
:::

## 独自の招待リンクを作成して使用する

上記のように、招待リンクを生成するには、`client_id`パラメータをClient IDに置き換える必要があります。 アプリのIDを確認するには、もう一度"Applications"セクション内の[My Apps](https://discordapp.com/developers/applications/me)ページに戻り、ボットアプリケーションを選択します。

アプリのIDをリンクテンプレートに挿入し、ブラウザーでアクセスしてください。 そうすると次のようにボットのユーザー名とアバターが表示されるはずです。

![ボット認証画面](~@/images/A8l70bj.png)

追加したいサーバーを選択し、"Authorize"をクリックします。 ボットを追加するには、そのサーバーで「サーバーの管理」権限が必要になることに注意してください。 追加が完了すると次の確認メッセージが表示されます。

![認証したボット](~@/images/BAUsjyg.png)

おめでとうございます ！ これでDiscordサーバーにボットが正常に追加されました。 サーバーのメンバーリストに次のように表示されます。

![サーバーのユーザーリストにあるボット](~@/images/6qTlDW0.png)
