---
aliases:
- /ja/guides/basic_agent_usage/centos/
further_reading:
- link: /logs/
  tag: Documentation
  text: ログの収集
- link: /infrastructure/process/
  tag: Documentation
  text: プロセスの収集
- link: /tracing/
  tag: Documentation
  text: トレースの収集
- link: /agent/basic_agent_usage/#agent-architecture
  tag: Documentation
  text: Agent のアーキテクチャを詳しく見る
- link: /agent/guide/network#configure-ports
  tag: Documentation
  text: インバウンドポートの構成
kind: documentation
platform: CentOS
title: CentOS (および Rocky/Alma Linux) の基本的な Agent の使い方
---

## 概要

このページでは、CentOS とその派生製品である Rocky Linux と Alma Linux 用の Datadog Agent の基本的な機能について説明します。Datadog Agent のインストールは、CentOs 用 [Agent のインストール手順][1]に従ってください。

64-bit x86 および Arm v8 アーキテクチャ用のパッケージをご用意しています。その他のアーキテクチャについては、ソースインストールをご利用ください。

**注**: CentOS 6 以降は、64 ビット x86 アーキテクチャでサポートされています。CentOS/Rocky/Alma 8 以降は、64 ビット Arm v8 アーキテクチャでサポートされています。

## コマンド

Agent v6 & v7 では、オペレーティングシステムから提供されるサービスマネージャーが Agent のライフサイクルを担う一方で、他のコマンドは Agent バイナリから直接実行する必要があります。Agent v5 では、ほぼすべてがサービスマネージャーによって実行されます。

{{< tabs >}}
{{% tab "Agent v6 & v7" %}}

### CentOS 7 以降

| 説明                        | コマンド                                                |
|------------------------------------|--------------------------------------------------------|
| Agent をサービスとして起動           | `sudo systemctl start datadog-agent`                   |
| サービスとして実行中の Agent の停止    | `sudo systemctl stop datadog-agent`                    |
| サービスとして実行中の Agent の再起動 | `sudo systemctl restart datadog-agent`                 |
| Agent サービスのステータス            | `sudo systemctl status datadog-agent`                  |
| 実行中の Agent のステータスページ       | `sudo datadog-agent status`                            |
| フレアの送信                         | `sudo datadog-agent flare`                             |
| コマンドの使用方法の表示              | `sudo datadog-agent --help`                            |
| チェックの実行                        | `sudo -u dd-agent -- datadog-agent check <CHECK_NAME>` |

### CentOS 6

| 説明                        | コマンド                                                |
|------------------------------------|--------------------------------------------------------|
| Agent をサービスとして起動           | `sudo start datadog-agent`                             |
| サービスとして実行中の Agent の停止    | `sudo stop datadog-agent`                              |
| サービスとして実行中の Agent の再起動 | `sudo restart datadog-agent`                           |
| Agent サービスのステータス            | `sudo status datadog-agent`                            |
| 実行中の Agent のステータスページ       | `sudo datadog-agent status`                            |
| フレアの送信                         | `sudo datadog-agent flare`                             |
| コマンドの使用方法の表示              | `sudo datadog-agent --help`                            |
| チェックの実行                        | `sudo -u dd-agent -- datadog-agent check <CHECK_NAME>` |

{{% /tab %}}
{{% tab "Agent v5" %}}

| 説明                        | コマンド                                           |
|------------------------------------|---------------------------------------------------|
| Agent をサービスとして起動           | `sudo service datadog-agent start`                |
| サービスとして実行中の Agent の停止    | `sudo service datadog-agent stop`                 |
| サービスとして実行中の Agent の再起動 | `sudo service datadog-agent restart`              |
| Agent サービスのステータス            | `sudo service datadog-agent status`               |
| 実行中の Agent のステータスページ       | `sudo service datadog-agent info`                 |
| フレアの送信                         | `sudo service datadog-agent flare`                |
| コマンドの使用方法の表示              | `sudo service datadog-agent`                      |
| チェックの実行                        | `sudo -u dd-agent -- dd-agent check <CHECK_NAME>` |

**注**: ご使用のシステムで `service` ラッパーを使用できない場合は、以下を使用してください。

* `upstart` ベースのシステムの場合: `sudo start/stop/restart/status datadog-agent`
* `systemd` ベースのシステムの場合: `sudo systemctl start/stop/restart/status datadog-agent`

[サービスライフサイクルコマンドについては、こちらを参照してください][2]。

{{% /tab %}}
{{< /tabs >}}


## コンフィギュレーション

{{< tabs >}}
{{% tab "Agent v6 & v7" %}}
Agent の構成ファイルおよびフォルダーの場所:

* `/etc/datadog-agent/datadog.yaml`

[インテグレーション][1]用構成ファイルの場所

* `/etc/datadog-agent/conf.d/`

[1]: /ja/integrations/
{{% /tab %}}
{{% tab "Agent v5" %}}

Agent の構成ファイルおよびフォルダーの場所

* `/etc/dd-agent/datadog.conf`

[インテグレーション][1]用構成ファイルの場所

* `/etc/dd-agent/conf.d/`

[1]: /ja/integrations/
{{% /tab %}}
{{< /tabs >}}

## トラブルシューティング

[Agent のトラブルシューティングに関するドキュメント][2]を参照してください。

## 埋め込み Agent の使用

Agent には、埋め込み Python 環境が `/opt/datadog-agent/embedded/` に含まれています。`python`、`pip` などの共通バイナリは `/opt/datadog-agent/embedded/bin/` に含まれています。

詳細については、[埋め込み Agent へのパッケージの追加方法][3]の手順を参照してください。

## その他の参考資料

{{< partial name="whats-next/whats-next.html" >}}

[1]: https://app.datadoghq.com/account/settings/agent/latest?platform=centos
[2]: /ja/agent/troubleshooting/
[3]: /ja/developers/guide/custom-python-package/