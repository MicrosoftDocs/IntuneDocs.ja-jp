---
title: "Intune データ ウェアハウスを使用する | Microsoft Docs"
description: "Intune データ ウェアハウスを使用して、社内のモバイル環境を分析できるレポートを構築します。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2017
---
# <a name="use-the-intune-data-warehouse"></a>Intune データ ウェアハウスを使用する

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune データ ウェアハウスを使用して、社内のモバイル環境を分析できるレポートを構築します。 たとえば、次のようなレポートがあります。
-   ライセンス購入の最適化に利用できる Intune に登録されているユーザーの傾向
-   モバイル デバイスの状態を確認できるアプリと OS バージョンの内訳
-   ポリシーの更新をスムーズにロールアウトできる登録とデバイス コンプライアンスの傾向

データ ウェアハウスを使用すると、モバイル環境について Azure Portal よりも詳細な情報にアクセスできます。 Intune データ ウェアハウスでは、次の情報にアクセスできます。

  -  Intune の履歴データ
  -  日単位の更新データ
  -  OData 標準を使用するデータ モデル

> [!Important]  
> データ ウェアハウスの最新機能については、ベータ バージョンを使用して試すことができます。 ベータ バージョンを使用するには、URL にクエリ パラメーター `api-version=beta` を含める必要があります。 ベータ バージョンは、サポートされるサービスとして一般公開される前の機能を提供しています。 Intune に新しい機能が追加されると、ベータ バージョンの動作とデータ コントラクトが変わる可能性があります。 カスタム コードまたはレポート ツールがベータ バージョンに依存していると、今後の更新プログラムで使用できなくなる可能性があります。 <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**次のステップ**

- リンクを取得し、Power BI を使用して分析します。 手順については、「[Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md)」(Power BI で Intune データ ウェアハウスに接続する) を参照してください。
- Intune データ ウェアハウス API、データ モデル、エンティティ間の関係の詳細については、<!-- , and an example of creating a custom client to retrieve data,-->「[Intune データ ウェアハウス API](reports-nav-intune-date-warehouse.md)」を参照してください。