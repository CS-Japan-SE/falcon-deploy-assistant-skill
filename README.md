# CrowdStrike Falcon Deploy Assistant

CrowdStrike Falcon を各クラウド・プラットフォームへデプロイする方法を Claude Code が説明してくれるスラッシュコマンドです。

## セットアップ

```bash
git clone https://github.com/CS-Japan-SE/falcon-deploy-assistant-skill.git
cd falcon-deploy-assistant-skill
claude  # このディレクトリで Claude Code を起動すると /falcon-deploy-assistant が使えるようになります
```

## 使い方

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

### クラウドプロバイダー

| ターゲット | リポジトリ |
| --- | --- |
| Azure | [CrowdStrike/Cloud-Azure](https://github.com/CrowdStrike/Cloud-Azure) |
| AWS | [CrowdStrike/Cloud-AWS](https://github.com/CrowdStrike/Cloud-AWS) |
| GCP | [CrowdStrike/Cloud-GCP](https://github.com/CrowdStrike/Cloud-GCP) + 関連外部リポジトリ |
| OCI | [CrowdStrike/Cloud-OCI](https://github.com/CrowdStrike/Cloud-OCI) |

### コンテナプラットフォーム

| ターゲット | リポジトリ |
| --- | --- |
| Kubernetes | [CrowdStrike/falcon-helm](https://github.com/CrowdStrike/falcon-helm) |
| OpenShift | [CrowdStrike/falcon-operator](https://github.com/CrowdStrike/falcon-operator) |

### 汎用ツール

| ターゲット | リポジトリ |
| --- | --- |
| Scripts | [CrowdStrike/falcon-scripts](https://github.com/CrowdStrike/falcon-scripts) |

## ファイル構成

```
falcon-deploy-assistant-skill/
├── README.md
└── .claude/
    └── commands/
        └── falcon-deploy-assistant.md   # /falcon-deploy-assistant スラッシュコマンド定義
```
