# CrowdStrike Falcon Deploy Assistant

CrowdStrike Falconセンサー を各クラウド・プラットフォームへデプロイする方法を Claude Code が説明してくれるSkillです。

## 使い方

### 方法 1 — クローン不要（チャットで直接使う）

Claude Code のチャットに以下のように入力するだけで使えます。

```
AWS EC2が1000台ある環境へ、Falconセンサーを展開する方法を教えて。
以下のファイルの手順に従ってください:
https://raw.githubusercontent.com/CS-Japan-SE/falcon-deploy-assistant-skill/main/.claude/commands/falcon-deploy-assistant.md
```

Claude Code がファイルを取得し、中の指示に従ってデプロイ手順を説明してくれます。

### 方法 2 — スラッシュコマンドとして登録する

リポジトリをクローンして Claude Code を起動すると、`/falcon-deploy-assistant` スラッシュコマンドとして使えるようになります。

```bash
git clone https://github.com/CS-Japan-SE/falcon-deploy-assistant-skill.git
cd falcon-deploy-assistant-skill
claude  # このディレクトリで Claude Code を起動すると /falcon-deploy-assistant が使えるようになります
```

Claude Code のチャットで `/falcon-deploy-assistant` と入力するだけです。

```
/falcon-deploy-assistant
```

クラウドプロバイダーやデプロイ対象を聞かれるので答えると、該当するドキュメントを CrowdStrike の公式リポジトリから取得してデプロイ手順を説明してくれます。

日本語で説明してほしい場合は、以下のように指示してください。

```
/falcon-deploy-assistant 日本語で説明してください
```

または、コマンド実行後に「日本語で説明してください」と追加で伝えても構いません。

## 対応リポジトリ

### AWS

| 統合方法 | リポジトリ |
| --- | --- |
| SSM Distributor | [CrowdStrike/terraform-aws-ssm-distributor](https://github.com/CrowdStrike/terraform-aws-ssm-distributor) |
| ECS Fargate | [CrowdStrike/terraform-aws-ecs-fargate](https://github.com/CrowdStrike/terraform-aws-ecs-fargate) |
| EKS Protection | [CrowdStrike/aws-eks-protection](https://github.com/CrowdStrike/aws-eks-protection) |
| EC2 Image Builder | [CrowdStrike/aws-ec2-image-builder](https://github.com/CrowdStrike/aws-ec2-image-builder) |
| CloudFormation (ECS) | [CrowdStrike/aws-cloudformation-falcon-sensor-ecs](https://github.com/CrowdStrike/aws-cloudformation-falcon-sensor-ecs) |
| Beanstalk / WorkSpaces / 他 | [CrowdStrike/Cloud-AWS](https://github.com/CrowdStrike/Cloud-AWS) |

### Azure

| 統合方法 | リポジトリ |
| --- | --- |
| VM Extension | [CrowdStrike/azure-vm-extension](https://github.com/CrowdStrike/azure-vm-extension) |
| Intune / AVD / Dev Box / 他 | [CrowdStrike/Cloud-Azure](https://github.com/CrowdStrike/Cloud-Azure) |

### GCP

| 統合方法 | リポジトリ |
| --- | --- |
| VM Manager OS Policy | [CrowdStrike/gcp-vm-manager-os-policy](https://github.com/CrowdStrike/gcp-vm-manager-os-policy) |
| GKE Protection | [CrowdStrike/gcp-gke-protection](https://github.com/CrowdStrike/gcp-gke-protection) |
| その他 | [CrowdStrike/Cloud-GCP](https://github.com/CrowdStrike/Cloud-GCP) |

### OCI

| 統合方法 | リポジトリ |
| --- | --- |
| Oracle Cloud Infrastructure | [CrowdStrike/Cloud-OCI](https://github.com/CrowdStrike/Cloud-OCI) |

### コンテナ・Kubernetes

| 統合方法 | リポジトリ |
| --- | --- |
| Helm (Kubernetes) | [CrowdStrike/falcon-helm](https://github.com/CrowdStrike/falcon-helm) |
| Operator (OpenShift) | [CrowdStrike/falcon-operator](https://github.com/CrowdStrike/falcon-operator) |
| EKS Protection | [CrowdStrike/aws-eks-protection](https://github.com/CrowdStrike/aws-eks-protection) |
| GKE Protection | [CrowdStrike/gcp-gke-protection](https://github.com/CrowdStrike/gcp-gke-protection) |
| Terraform (kubectl) | [CrowdStrike/terraform-kubectl-falcon](https://github.com/CrowdStrike/terraform-kubectl-falcon) |

### 構成管理・汎用ツール

| 統合方法 | リポジトリ |
| --- | --- |
| Ansible | [CrowdStrike/ansible_collection_falcon](https://github.com/CrowdStrike/ansible_collection_falcon) |
| Scripts (Linux/Windows/macOS) | [CrowdStrike/falcon-scripts](https://github.com/CrowdStrike/falcon-scripts) |
| Installer (standalone CLI) | [CrowdStrike/falcon-installer](https://github.com/CrowdStrike/falcon-installer) |

## ファイル構成

```
falcon-deploy-assistant-skill/
├── README.md
└── .claude/
    └── commands/
        └── falcon-deploy-assistant.md   # /falcon-deploy-assistant スラッシュコマンド定義
```
