---
categories:
- cloud
- azure
dependencies: []
description: Azure Recovery Service Vault のキーメトリクスを追跡します。
doc_link: https://docs.datadoghq.com/integrations/azure_recovery_service_vault/
draft: false
git_integration_title: azure_recovery_service_vault
has_logo: true
integration_id: ''
integration_title: Azure Recovery Service Vault
integration_version: ''
is_public: true
kind: integration
manifest_version: '1.0'
name: azure_recovery_service_vault
public_title: Datadog-Azure Recovery Service Vault インテグレーション
short_description: Azure Recovery Service Vault のキーメトリクスを追跡します。
version: '1.0'
---

## 概要

Azure Recovery Service Vault インテグレーションは、Microsoft Azure 上で動作する Recovery Service Vault の健全性を監視するのに役立ちます。

Datadog Azure インテグレーションは、Azure Recovery Service Vault からメトリクスを収集できますが、VM に Datadog Agent をインストールすることを[推奨][1]します。組織が Datadog の US3 サイトにあり、Azure で Datadog リソースを構成している場合は、[Azure Native インテグレーション手動セットアップガイド][2]の手順を使用してください。**すべてのサイト**は、[Azure インテグレーション手動セットアップガイド][3]または[Azure プログラム管理ガイド][4]の手順を使用できます。

## セットアップ

### インストール

[Microsoft Azure インテグレーション][5]をまだセットアップしていない場合は、最初にセットアップします。それ以上のインストール手順はありません。

## 収集データ

### メトリクス
{{< get-metrics-from-git "azure_recovery_service_vault" >}}


### イベント

Azure Recovery Service Vault インテグレーションには、イベントは含まれません。

### サービスのチェック

Azure Recovery Service Vault インテグレーションには、サービスのチェック機能は含まれません。

## トラブルシューティング

ご不明な点は、[Datadog のサポートチーム][7]までお問い合わせください。


[1]: https://www.datadoghq.com/blog/dont-fear-the-agent/
[2]: https://docs.datadoghq.com/ja/integrations/guide/azure-native-manual-setup/#virtual-machine-agent
[3]: https://docs.datadoghq.com/ja/integrations/guide/azure-manual-setup/#agent-installation
[4]: https://docs.datadoghq.com/ja/integrations/guide/azure-programmatic-management/#datadog-azure-vm-extension
[5]: https://docs.datadoghq.com/ja/integrations/azure/
[6]: https://github.com/DataDog/dogweb/blob/prod/integration/azure_recovery_service_vault/azure_recovery_service_vault_metadata.csv
[7]: https://docs.datadoghq.com/ja/help/