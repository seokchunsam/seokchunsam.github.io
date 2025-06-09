# AWS Certificate Manager (ACM)

## ✅ 인증서 만료 알림 자동화

- 인증서 만료 14일 전 알림이 필요할 경우:
  - EventBridge에서 `aws.acm` 이벤트 수신
  - 조건: `DaysToExpiry < 14`
  - 알림 전송: SNS + 이메일 구독

## ✅ 구성 흐름

1. EventBridge Rule 생성 (이벤트 소스: `aws.acm`)
2. 필터: DaysToExpiry < 14
3. 대상: SNS 주제
4. SNS 주제에 이메일 구독



# AWS Certificate Manager (ACM)

## ✅ 証明書の有効期限通知の自動化

- 証明書の有効期限が14日未満になると、通知メールを送信する構成が可能です。
  - EventBridgeで `aws.acm` イベントを受信
  - 条件：`DaysToExpiry < 14`
  - 通知方法：SNSトピック → メール購読

## ✅ 構成手順

1. EventBridgeルールを作成（イベントソース：`aws.acm`）
2. フィルター条件：DaysToExpiry < 14
3. ターゲット：SNSトピック
4. SNSトピックにメールアドレスを購読
