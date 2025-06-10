# VPC 및 네트워킹 보안

## ✅ VPC Flow Logs가 CloudWatch Logs에 전송되지 않는 문제 (문제 #455)

### 💡 상황
- VPC Flow Logs를 CloudWatch Logs에 전송하도록 구성했으나, 로그가 전혀 나타나지 않음

### 🧠 원인
- IAM 역할에 `logs:CreateLogGroup` 권한이 없으면 로그 그룹 생성이 불가하여 로그 전송도 실패함

### ✅ 필요한 IAM 권한
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



