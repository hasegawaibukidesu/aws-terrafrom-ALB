# AWS ALB + EC2 + Nginx 構成

## ■ 概要
AWS上でALBを経由してEC2のNginxにアクセスできる構成を構築しました。

## ■ 構成図
User → ALB → EC2 → Nginx

## ■ 使用技術
- AWS
  - ALB
  - EC2
  - VPC
  - Security Group
- Nginx

## ■ アクセス方法
ALBのDNS名にブラウザでアクセス

## ■ 工夫した点 / 学んだこと
- ALB経由での通信の流れを理解
- セキュリティグループの設定の重要性

## ■ 詰まったポイント
### ① 502 Bad Gateway
原因：
- Nginxが起動していなかった / ポート設定ミス

対応：
- Nginxの起動確認
- ポート80の疎通確認

### ② EC2に接続できない
原因：
- キーペアの設定ミス

対応：
- 新しいキーペアで再作成

## ■ 今後の改善
- Terraformで構成管理
- Docker化
- CI/CD導入（GitHub Actionsなど）