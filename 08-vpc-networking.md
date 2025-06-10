# VPC 및 네트워킹 보안

## ✅ VPC Flow Logs가 CloudWatch Logs에 전송되지 않는 문제

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
```


### 💡 상황
 - 3개의 AZ에 걸친 EC2 인스턴스에 NLB를 통해 트래픽 라우팅

 요구사항: EC2 인스턴스가 오직 NLB에서 오는 트래픽만 허용해야 함

### ✅ 가장 효율적인 방법
 - EC2 인스턴스에 연결된 보안 그룹에서 NLB의 ENI를 source로 설정

 - 보안 그룹은 상태 저장(스테이트풀)이며, 운영 오버헤드가 낮음

### ❌ 피해야 할 방법
 - NACL 사용 → 상태 비저장이고 복잡

 - 타사 방화벽 사용 → 과도한 오버헤드

 - NLB는 보안 그룹 직접 사용 불가
