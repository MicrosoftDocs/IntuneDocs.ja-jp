---
title: "管理対象の業務用アプリのデータをワイプする | Microsoft Intune"
description: "リモートでデバイスから会社のデータを選択的に削除する方法について説明します。"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d32a66ee283906586e25173e736c02ee8bf23042


---

# <a name="wipe-managed-company-app-data-with-microsoft-intune"></a>管理対象の業務用アプリのデータを Microsoft Intune でワイプする
デバイスが紛失や盗難にあった場合、または従業員が離職した場合、会社のアプリのデータがデバイスから削除されたことを確認する必要があります。 ただし、個人のデータをデバイスから削除するのは好ましくありません。そのデバイスの所有者が従業員である場合はなおさらです。

会社のアプリ データを選択して削除するには、このトピックの手順を使用してワイプ要求を作成します。 ワイプ要求の完了後、次にデバイス上でアプリが実行されると、そのアプリから会社のデータが削除されます。
>[!NOTE]
> アプリケーションからネイティブ アドレス帳に直接同期された連絡先が削除されます。 ネイティブ アドレス帳から別の外部ソースに同期された連絡先はワイプできません。 現在、これは Microsoft Outlook アプリにのみ適用されます。



## <a name="create-a-wipe-request"></a>ワイプ要求の作成

1.  **[Intune モバイル アプリケーション管理]** ブレードで **[ワイプ要求]** タイルを選択します。

    ![[Intune モバイル アプリケーション管理] ブレードと [概要] タイルのスクリーンショット](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  **[新しいワイプ要求]** を選択します。 **[新しいワイプ要求]** ブレードが開きます。

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  **[ユーザー]** を選択して **[ユーザー]** ブレードを開き、アプリ データをワイプするユーザーを選びます。

4.  **[デバイス]** を選択します。   **[デバイス]** ブレードが開き、選んだユーザーに関連付けられているすべてのデバイスが一覧表示されます。  ワイプするデバイスを選びます。

5.  **[新しいワイプ要求]** ブレードに戻ります。 **[OK]** を選択してワイプ要求を行います。 サービスにより、デバイス上の保護されている各アプリに対して、個別のワイプ要求が作成され、追跡されます。


![[ワイプ要求] タイルのスクリーンショット ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## <a name="monitor-your-wipe-requests"></a>ワイプ要求を監視する
 **[Intune モバイル アプリケーション管理]** ブレードの **[ワイプ要求]** タイルに、集計レポートが表示されます。  これには保留中の要求およびエラーの数を含めた全体的な状態が表示されます。 次に示す手順に従って詳しい情報を確認できます。

1.  **[Intune モバイル アプリケーション管理]** ブレードで、**[ワイプ要求]** タイルを選択して **[ワイプ要求]** ブレードを開きます。

2.  **[ワイプ要求]** ブレードでは、要求をユーザー別にグループ化して一覧表示できます。 ワイプ要求はデバイスで実行されている保護アプリごとに作成されるため、1 ユーザーに対する要求が複数ある場合があります。 状態は、ワイプ要求が **[保留中]**、**[失敗]**、または **[成功]**のいずれかであることを示します。

ワイプを実行するにはユーザーがアプリを開く必要があるため、ワイプには要求後最大で 30 分かかる場合があります。

[保留中] 状態のワイプは、手動で削除するまで表示されます。  手動でワイプ要求を削除する場合は、右クリックして [削除] を選択します。

### <a name="see-also"></a>関連項目
[モバイル アプリケーション管理ポリシーを使用してデータを保護する](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Azure Portal の使用](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Dec16_HO2-->

