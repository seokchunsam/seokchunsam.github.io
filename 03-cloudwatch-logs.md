# CloudWatch Logs와 Lambda 연동

## Lambda → CloudWatch Logs 권한

Lambda 함수가 CloudWatch Logs에 로그를 출력하려면 다음 권한이 필요

```json
{
  "Effect": "Allow",
  "Action": [
    "logs:CreateLogGroup",
    "logs:CreateLogStream",
    "logs:PutLogEvents"
  ],
  "Resource": "*"
}
```



# CloudWatch LogsとLambdaの連携

## Lambda → CloudWatch Logs への書き込み権限

Lambda関数がCloudWatch Logsにログを出力するには、次のIAMポリシーが必要

```json
{
  "Effect": "Allow",
  "Action": [
    "logs:CreateLogGroup",
    "logs:CreateLogStream",
    "logs:PutLogEvents"
  ],
  "Resource": "*"
}
```
