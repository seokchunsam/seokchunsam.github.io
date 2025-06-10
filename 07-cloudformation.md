# AWS CloudFormation

## ✅ 스택 삭제 실패(DELETE_FAILED) 원인

- CloudFormation이 생성한 보안 그룹이 **다른 리소스에 의해 참조**되면 삭제 불가
- 참조가 해제되지 않으면 스택 삭제도 실패

## ✅ 해결 방법: 리소스 보존(Retain)

- CloudFormation 리소스를 삭제하지 않고 남기려면 `Retain` 정책 사용

```yaml
DeletionPolicy: Retain

또는 CLI에서 --retain-resources 플래그 사용 가능



# AWS CloudFormationリソース保持設定

## ✅ スタック削除失敗（DELETE_FAILED）の原因

- CloudFormationで作成されたセキュリティグループが、他のリソースに参照されていると削除に失敗します。

## ✅ 解決方法：リソース保持（Retain）

- リソースを削除せずにスタックから除外するには、`Retain`ポリシーを使用します。

```yaml
DeletionPolicy: Retain

またはCLIから --retain-resources 使用可能
