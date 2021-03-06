---
title: Log Analytics のアラートを Azure Alerts に拡張 (コピー) する - 概要
description: アラートを OMS ポータル内の Log Analytics から Azure Alerts にコピーするプロセスの概要について説明し、お客様の一般的な懸念に対応する詳細を示します。
author: msvijayn
services: azure-monitor
ms.service: azure-monitor
ms.topic: conceptual
ms.date: 05/24/2018
ms.author: vinagara
ms.component: alerts
ms.openlocfilehash: 6484142eafa8388117c1e96ab31eefeab188e488
ms.sourcegitcommit: 6eb14a2c7ffb1afa4d502f5162f7283d4aceb9e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36750274"
---
# <a name="extend-log-analytics-alerts-to-azure-alerts"></a>Log Analytics アラートを Azure Alerts に拡張する
最近まで、Azure Log Analytics には、Log Analytics のデータに基づいて状態を事前にユーザーに通知できる独自のアラート機能が含まれていました。 Microsoft Operations Management Suite ポータルでアラート ルールを管理していました。 新しいアラートのエクスペリエンスにより、Microsoft Azure のさまざまなサービスにわたってアラートが統合されました。 これは Azure Portal の Azure Monitor で **[アラート]**  として提供されており、Log Analytics と Azure Application Insights 両方のアクティビティ ログ、メトリック、およびログからのアラートをサポートしています。 

## <a name="benefits-of-extending-your-alerts"></a>アラートを拡張するメリット
Azure Portal でアラートの作成と管理を行うことには、以下のようにいくつかの利点があります。

- 作成や表示が可能なアラートが 250 件のみである Operations Management Suite ポータルとは異なり、Azure Alerts にこのような制限はありません。
- Azure Alerts からは、すべての種類のアラートを管理、列挙、表示できます。 以前それが可能であったのは、Log Analytics のアラートについてのみでした。
- [Azure Monitor ロール](monitoring-roles-permissions-security.md)を使用して、ユーザーのアクセスを監視とアラートのみに制限できます。
- Azure Alerts では、[アクション グループ](monitoring-action-groups.md)を使用できます。 これにより、アラートごとに複数のアクションを指定できます。 SMS の使用、音声通話の送信、Azure Automation Runbook の呼び出し、webhook の呼び出し、および IT Service Management (ITSM) Connector の構成が可能です。 

## <a name="process-of-extending-your-alerts"></a>アラートを拡張するプロセス
Log Analytics のアラートを Azure Alerts に移すプロセスに、アラートの定義、クエリ、構成の変更は含まれません。 必要とされる唯一の変更として、Azure では、アクション グループを使用してすべてのアクションを実行します。 アクション グループが既にアラートに関連付けられている場合、それらは Azure に拡張されるときに含められます。

> [!NOTE]
> Microsoft は 2018 年 5 月 14 日より、完了するまで反復される一連の処理で、Log Analytics で作成されたアラートを自動的に Azure Alerts に拡張します。 [アクション グループ](monitoring-action-groups.md)の作成でなんらかの問題がある場合は、[これらの修復手順](monitoring-alerts-extend-tool.md#troubleshooting)を使用して、アクション グループを自動作成させます。 2018 年 7 月 5日まで、これらの手順を使用できます。 
> 

Log Analytics ワークスペース内のアラートを Azure に拡張するスケジュールを設定しても、それらのアラートは引き続き機能し、構成を損なうことは決してありません。 スケジュールが設定されると、アラートを一時的に変更できなくなる場合がありますが、この期間中、引き続き新しい Azure Alerts を作成できます。 Operations Management Suite ポータルからアラートの編集や作成をしようとする場合は、Log Analytics ワークスペースから作成を続けるオプションが用意されています。 Azure Portal 内の Azure Alerts からそれらを作成することもできます。

 ![Log Analytics または Azure Alerts からアラートを作成するオプションのスクリーンショット](./media/monitor-alerts-extend/ScheduledDirection.png)

> [!NOTE]
> アラートを Log Analytics から Azure に拡張しても、アカウントに料金は発生しません。 クエリベースの Log Analytics アラートに対して Azure Alerts を使用しても、[Azure Monitor の価格ポリシー](https://azure.microsoft.com/pricing/details/monitor/)に記載されている制限や条件内の使用であれば課金されません。  


### <a name="how-to-extend-your-alerts-voluntarily"></a>アラートを自主的に拡張する方法
アラートを Azure Alerts に拡張するには、Operations Management Suite ポータルに用意されているウィザードを使用するか、API を使用してプログラムによって拡張します。 詳細については、[Operations Management Suite ポータルおよび API を使用してアラートを Azure に拡張する方法](monitoring-alerts-extend-tool.md)に関するページを参照してください。

## <a name="experience-after-extending-your-alerts"></a>アラート拡張後のエクスペリエンス
アラートは、Azure Alerts に拡張された後、前とまったく変わりなく、管理のために Operations Management Suite ポータルで引き続き使用できます。

![アラートが一覧表示されている Operations Management Suite ポータルのスクリーンショット](./media/monitor-alerts-extend/PostExtendList.png)

Operations Management Suite ポータルで、既存のアラートの編集や新しいアラートの作成を行おうとすると、自動的に Azure Alerts にリダイレクトされます。  

> [!NOTE]
> アラートを追加または編集する必要がある個人に割り当てられたアクセス許可が、Azure で正しく割り当てられていることを確認してください。 どのようなアクセス許可を付与する必要があるかを理解するには、[Azure Monitor と Azure Alerts を使用するためのアクセス許可](monitoring-roles-permissions-security.md)についての記事を参照してください。  
> 

アラートは引き続き、[Log Analytics API](../log-analytics/log-analytics-api-alerts.md) や [Log Analytics リソース テンプレート](../monitoring/monitoring-solutions-resources-searches-alerts.md)から作成できます。 これを行うときには、アクション グループを含める必要があります。

## <a name="next-steps"></a>次の手順

* [Log Analytics から Azure へのアラート拡張の開始する](monitoring-alerts-extend-tool.md)ためのツールについて学習する。
* [Azure Alerts のエクスペリエンス](monitoring-overview-unified-alerts.md)の詳細について学習する。
* [Azure Alerts でのログ アラート](monitor-alerts-unified-log.md)の作成方法について学習します。
