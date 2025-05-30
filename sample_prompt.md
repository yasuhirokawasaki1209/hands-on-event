# instruction
- あなたはQAエンジニアです。
- #testcaseの内容のテストスクリプトを#ruleに従って実装してください。
- 実装が完了したら、それをplaywrightで実行してください。

# rule
- playwrightを用いてください
- 言語はtypescriptを用いてください
- 要素を取得する際は、"# sample"の方法を参考にしてください

# sample
- page.getByRole()
- page.getByLavel()

# testcase 
- name: "素泊まりプランの予約が行えること"
  given: "https://hotel-example-site.takeyaqa.dev/ja/reserve.html?plan-id=4"にアクセス
  steps:
    - "氏名"入力欄に"テスト太郎"と入力
    - "確認のご連絡"セレクトボックスで"希望しない"を選択
    - "予約内容を確認する"ボタンをクリック
    - "https://hotel-example-site.takeyaqa.dev/ja/confirm.html"に遷移していることを確認する
    - "この内容で予約する"ボタンをクリック
  expected: ”予約を完了しました”のダイアログが表示されること

  - name: "出張ビジネスプランプランの予約が行えること"
  given: "https://hotel-example-site.takeyaqa.dev/ja/reserve.html?plan-id=5"にアクセス
  steps:
  　- "朝食バイキング"にチェックを入れる
    - "氏名"入力欄に"テスト太郎"と入力
    - "確認のご連絡"セレクトボックスで"希望しない"を選択
    - "予約内容を確認する"ボタンをクリック
    - "https://hotel-example-site.takeyaqa.dev/ja/confirm.html"に遷移していることを確認する
    - "この内容で予約する"ボタンをクリック
    - キャプチャを撮る
  expected: ”予約を完了しました”のダイアログが表示されること

# output
- test-hands-on2.spec.tsというファイル名で出力してください
