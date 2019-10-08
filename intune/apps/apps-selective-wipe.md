---
title: アプリから会社のデータのみをワイプする方法
titleSuffix: Microsoft Intune
description: Microsoft Intune を利用している Intune マネージド アプリから選択的に会社のデータのみをワイプする方法について説明します。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 212fe3294a40ce006e4e60e4ce4f0cf8881159e4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725024"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Intune で管理されているアプリから会社のデータをワイプする方法

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

デバイスが紛失や盗難にあった場合、または従業員が離職した場合、会社のアプリのデータがデバイスから削除されたことを確認する必要があります。 ただし、個人のデータをデバイスから削除するのは好ましくありません。デバイスが従業員所有のデバイスである場合はなおさらです。

>[!NOTE]
> 現在、Intune マネージド アプリから会社のデータをワイプできるプラットフォームは、iOS、Android、および Windows 10 だけです。 Intune 管理対象アプリは、Intune アプリ SDK を含み、組織用のライセンスのあるユーザー アカウントを持つアプリケーションです。 アプリの選択的ワイプを有効にするために、アプリケーション保護ポリシーのデプロイは必要ありません。

会社のアプリ データを選択して削除するには、このトピックの手順を使用してワイプ要求を作成します。 ワイプ要求の完了後、次にデバイス上でアプリが実行されると、そのアプリから会社のデータが削除されます。 管理者は、ワイプ要求を作成するだけでなく、アプリケーション保護ポリシー (APP) アクセス設定の条件が満たされないときの新しいアクションとして、組織のデータの選択的ワイプを構成することができます。 この機能を使うと、事前に構成した条件に基づいて、アプリケーションから組織の機密データを自動的に保護したり削除したりできます。

>[!IMPORTANT]
> アプリケーションからネイティブ アドレス帳に直接同期された連絡先が削除されます。 ネイティブ アドレス帳から別の外部ソースに同期された連絡先はワイプできません。 現在、これは Microsoft Outlook アプリにのみ適用されます。

## <a name="deployed-wip-policies-without-user-enrollment"></a>ユーザー登録なしでの WIP ポリシーの展開
使用している Windows 10 デバイスを登録することを MDM ユーザーに求めることなく、Windows 情報保護 (WIP) ポリシーを展開できるようになります。 この構成により、会社は WIP 構成に基づいて会社のドキュメントを保護することができ、一方、ユーザーは独自の Windows デバイスの管理を維持することができます。 WIP ポリシーを使用してドキュメントが保護されると、Intune 管理者は保護されたデータを選択的にワイプすることができます。 ユーザーとデバイスを選択してワイプ要求を送信することにより、WIP ポリシーを介して保護されたデータはすべて使用できなくなります。 Azure portal 内で Intune から、 **[クライアント アプリ]**  >  **[アプリの選択的ワイプ]** の順に選択します。 詳細については、「[Intune で Windows 情報保護 (WIP) アプリ保護ポリシーを作成して展開する](windows-information-protection-policy-create.md)」を参照してください。

## <a name="create-a-wipe-request"></a>ワイプ要求の作成

1. [Azure ポータル](https://portal.azure.com)にサインインします。

2. **[すべてのサービス]** を選択し、フィルター ボックスに「**Intune**」と入力して、 **[Intune]** を選択します。 Intune ウィンドウが開いたら、 **[クライアント アプリ]** ウィンドウを選びます。

    ![Microsoft Intune ウィンドウのスクリーンショット](./media/apps-selective-wipe/apps-selective-wipe01.png)

3. **[クライアント アプリ]** ウィンドウで、 **[アプリの選択的ワイプ]** を選択します。

4. **[新しいワイプ要求]** を選択します。 **[新しいワイプ要求]** ウィンドウが開きます。

    ![[新しいワイプ要求] ウィンドウのスクリーンショット](./media/apps-selective-wipe/AzurePortal_MAM_NewWipeRequest.png)

5. ユーザーを選び、 **[選択]** を選んで、ワイプしたいアプリ データを持つユーザーを選択します。

6. 次に、 **[新しいワイプ要求]** ウィンドウで **[デバイス]** を選びます。 **[デバイスの選択]** ブレードが開き、選んだユーザーに関連付けられているデバイスの一覧が表示されます。また、このブレードには 2 つの列があり、デバイス名 (ユーザーによって定義されるフレンドリ名) とデバイスの種類 (デバイスのプラットフォーム) が示されます。 ワイプするデバイスを選びます。

7. **[新しいワイプ要求]** ウィンドウに戻ります。 **[OK]** を選んでワイプ要求を行います。

サービスでは、デバイス上の保護されているアプリごとにワイプ要求が作成および追跡され、そのワイプ要求にはユーザーが関連付けられています。

## <a name="monitor-your-wipe-requests"></a>ワイプ要求を監視する

ワイプ要求の全体的状態、保留中の要求の数、失敗の数がまとめてある概要レポートを設定できます。 さらに詳しい情報が必要な場合、次の手順を実行します。

1. **[クライアント アプリ] - [アプリの選択的ワイプ]** ウィンドウでは、要求をユーザー別にグループ化して一覧表示できます。 ワイプ要求はデバイスで実行されている保護アプリごとに作成されるため、1 ユーザーに対する要求が複数ある場合があります。 状態は、ワイプ要求が **[保留中]** 、 **[失敗]** 、または **[成功]** のいずれかであることを示します。

    ![[アプリの選択的ワイプ] ウィンドウでのワイプ要求の状態のスクリーンショット](./media/apps-selective-wipe/wipe-request-status-1.png)

さらに、デバイス名とそのデバイスの種類を確認することもできます。これは、レポートを読み取るときに役に立つことがあります。

>[!IMPORTANT]
> ワイプを実行するにはユーザーがアプリを開く必要があるため、ワイプには要求後最大で 30 分かかる場合があります。

## <a name="delete-a-wipe-request"></a>ワイプ要求の削除

[保留中] 状態のワイプは、手動で削除するまで表示されます。 ワイプ要求を手動で削除するには、次の手順を実行します。

1. **[クライアント アプリ] - [アプリの選択的ワイプ]** ウィンドウを開きます。

2. 一覧で削除するワイプ要求を右クリックし、 **[ワイプ要求の削除]** を選びます。

    ![[アプリの選択的ワイプ] ウィンドウでのワイプ要求の一覧のスクリーンショット](./media/apps-selective-wipe/delete-wipe-request.png)

3. 削除を確認するメッセージが表示されたら、 **[はい]** または **[いいえ]** を選択し、 **[OK]** をクリックします。

## <a name="see-also"></a>関連項目
[アプリ保護ポリシーとは](app-protection-policy.md)

[アプリ管理とは](app-management.md)