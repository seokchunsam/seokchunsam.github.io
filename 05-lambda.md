## 📄 `05-lambda.md` – Lambda 함수 이해

```markdown
# AWS Lambda 개요

## ✅ 로그 출력

- `console.log()` 등으로 로그 출력 시 CloudWatch Logs로 전송됨
- 로컬에 로그 파일을 저장하지 않음
- 로그가 보이지 않으면 IAM 권한 확인 필요

## ✅ EventBridge 트리거

- Lambda는 EventBridge 이벤트를 수신하여 실행될 수 있음
- 호출 권한이 없어 실행되지 않을 수 있음 → Lambda Permission 필수



## 📄 `ja/05-lambda.md`

```markdown
# AWS Lambdaの基礎

## ✅ ログ出力

- `console.log()`などのメソッドを使ってログを出力すると、CloudWatch Logsに自動的に送信されます。
- ローカルログファイルは使用されません。
- ログが表示されない場合、IAMロールに必要な権限があるか確認します。

## ✅ EventBridgeトリガー

- Lambda関数はEventBridgeイベントに応じて実行されるよう設定できます。
- 呼び出し権限がないとLambdaが起動しません → Lambda Permissionの設定が必要です。
