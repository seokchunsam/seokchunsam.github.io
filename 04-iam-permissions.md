## 📄 `04-iam-permissions.md` – IAM 권한 및 리소스 호출

```markdown
# IAM 권한 및 Lambda 호출 권한

## ✅ 외부 서비스에서 Lambda 호출 허용 (EventBridge 등)

- 외부 서비스가 Lambda를 호출하려면 Lambda 함수에 `AWS::Lambda::Permission` 리소스를 추가해야 함

```yaml
Type: AWS::Lambda::Permission
Properties:
  FunctionName: myLambdaFunction
  Action: lambda:InvokeFunction
  Principal: events.amazonaws.com



## 📄 `ja/04-iam-permissions.md`

```markdown
# IAM権限とリソース呼び出し

## ✅ Lambdaを外部サービスから呼び出す許可（例：EventBridge）

- Lambda関数を外部サービスから呼び出すには、Lambda関数に `AWS::Lambda::Permission` リソースを追加する必要があります。

```yaml
Type: AWS::Lambda::Permission
Properties:
  FunctionName: myLambdaFunction
  Action: lambda:InvokeFunction
  Principal: events.amazonaws.com
