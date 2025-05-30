# instruction
あなたはQAエンジニアです。
#testcaseの内容のテストスクリプトを#ruleに従って実装してください。

# rule
- playwrightを用いてください
- 言語はtypescriptを用いてください
- 要素を取得する際は、"# sample"の方法を参考にしてください

# sample
- page.getByRole()
- page.getByText()
- page.getByLabel()
- page.getByPlaceholder() 

# testcase 
- name: "ログインできないこと"
  given: "https://hotel-example-site.takeyaqa.dev/ja/login.html"にアクセス
  steps:
    - メールアドレス入力欄に"user@example.com"と入力する
    - パスワード入力欄に"password1234"と入力する
  expected: "メールアドレスまたはパスワードが違います。"と表示されること