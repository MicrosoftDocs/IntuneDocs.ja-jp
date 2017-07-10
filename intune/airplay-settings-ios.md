---
title: "Intune を使用した iOS デバイス向けの AirPlay 設定"
titleSuffix: Intune on Azure
description: "Intune を使用して、iOS デバイスを AirPlay 対応デバイスに自動接続する方法について説明します。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 47780d00b282fc260c16b06baa69091aad812b87
ms.contentlocale: ja-jp
ms.lasthandoff: 06/08/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Intune を使用した iOS デバイス向けの AirPlay 設定

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

これらの設定を使用すると、管理する iOS デバイスをネットワーク上の AirPlay 対応デバイス (Apple TV など) に接続することができます。
この機能を使用して、次のことができます。

- **デバイスとパスワードの一覧の構成** - ユーザーが、範囲内にある AirPlay デバイスに自動的に接続できるようにします。 AirPlay デバイスの名前とパスワードを使用して、AirPlay デバイスをプロビジョニングします。これにより、ユーザーが接続するときに、AirPlay デバイスの名前とパスワードを指定する必要がなくなります。
- **許可された出力先の構成** - AirPlay デバイスの一覧を (デバイス ID を使用して) 構成します。 エンド ユーザーには一覧を作成したデバイスだけ(監視対象のデバイスのみ) が表示され、そのデバイスにのみ接続できます。

## <a name="get-started"></a>作業開始

1. **[デバイス機能]** ブレードで **[AirPlay]** を選択します。
2. **[AirPlay]** ブレードで、次の操作の一方または両方を選択します。

## <a name="configure-a-device-and-password-list"></a>デバイスとパスワードの一覧を構成する

1. **[パスワード]** ブレードで、Airplay デバイス (例: **Contoso Apple TV**) の**デバイス名**と**パスワード**を入力します。
2. デバイスの詳細を入力したら、**[追加]** をクリックします。 **[デバイス名]** の一覧にデバイスが表示されます。
3. デバイスの追加を続けます。 終了したら **[OK]** を選択します。


## <a name="configure-allowed-destinations"></a>許可された出力先を構成する

1. **[Allowed destinations (supervised only)]\(許可された出力先 (監視のみ)\)** ブレードで、AirPlay デバイスの**デバイス ID** を入力します (例: 52:46:CD:51:83:4C)。
2. デバイス ID を入力したら、**[追加]** をクリックします。 **[デバイス ID]** 一覧に ID が表示されます。
3. デバイスの追加を続けます。 終了したら **[OK]** を選択します。

コンマ区切り値 (csv) ファイルから、デバイスとパスワード、および許可された出力先をインポートすることもできます。




