---
title: Android ストア アプリを Microsoft Intune に追加する
titleSuffix: ''
description: Google Play ストアから Microsoft Intune へ Android ストア アプリを追加する方法について説明します。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3153a470649e86bbafc9e8295a1c68532fc27c63
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72497696"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Android ストア アプリを Microsoft Intune に追加する

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

アプリをデバイスまたはユーザーのグループに割り当てる前に、最初にアプリを Microsoft Intune に追加する必要があります。 

## <a name="add-an-app"></a>アプリの追加

Azure Portal から Intune に Android Store アプリを追加するには、次の手順を実行します。

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) にサインインします。
3. **[Intune]** ウィンドウで、 **[クライアント アプリ]** を選択します。
4. **[クライアント アプリ]** ワークロード ウィンドウで、 **[管理]** の **[アプリ]** を選択します。
5. **[追加]** を選択します。
6. **[アプリの追加]** ウィンドウで、使用可能な **[ストア アプリ]** の種類で **[Android]** を選択します。
7. アプリ情報を構成するには、 **[構成]** を選択し、次の情報を入力します。 Android アプリの場合、[[Google Play ストア]](https://play.google.com/store) に移動し、展開するアプリを検索します。 アプリを選択し、アプリの詳細をメモします。 選択したアプリによっては、一部の値が自動的に入力されている場合があります。
    - **名前**: アプリの名前を入力します。この名前は会社のポータルに表示されます。 使用するアプリ名が一意であることを確認してください。 アプリ名が重複している場合、会社のポータルでは 1 つの名前のみがユーザーに表示されます。
    - **説明**:アプリの説明を入力します。 この説明は会社のポータルでユーザーに表示されます。
    - **[発行元]** : アプリの発行元の名前を入力します。
    - **[アプリ ストアの URL]** : 作成するアプリのアプリ ストア URL を入力します。
    - **[最低限のオペレーティング システム]** : アプリをインストールできる最も初期のバージョンのオペレーティング システムを一覧から選択します。 これよりも前のオペレーティング システムがアプリの割り当て先デバイスにインストールされている場合、そのアプリはインストールされません。
    - **[カテゴリ]** : (省略可能) 1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。 そうすると、会社のポータルを閲覧するときに、ユーザーがアプリを探しやすくなります。
    - **[会社のポータルでおすすめアプリとして表示します]** : ユーザーがアプリを参照するとき、会社のポータルのメイン ページにアプリ スイートが目立つように表示するには、このオプションを選びます。 利用可能インテントで展開されたアプリに適用されます。
    - **[情報 URL]** : このアプリに関する情報が含まれる Web サイトの URL を入力することもできます。 この URL は会社のポータルでユーザーに表示されます。
    - **[プライバシー URL]** : このアプリのプライバシー情報が含まれる Web サイトの URL を入力することもできます。 この URL は会社のポータルでユーザーに表示されます。
    - **[開発者]** : (省略可能) アプリ開発者の名前を入力します。
    - **[所有者]** : (省略可能) このアプリの所有者の名前 ("*人事部*" など) を入力します。
    - **[メモ]** : (省略可能) このアプリに関連付けるメモを入力します。
    - **[ロゴ]** : (省略可能) アプリに関連付けるアイコンをアップロードします。 ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。
8. **[OK]** を選択します。
9. **[追加]** を選択します。

作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。 

## <a name="next-steps"></a>次の手順

- [アプリをグループに割り当てる](apps-deploy.md)