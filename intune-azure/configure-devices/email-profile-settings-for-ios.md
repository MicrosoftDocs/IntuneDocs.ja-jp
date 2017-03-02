---
title: "iOS デバイス向けの Intune 電子メール設定 | Intune Azure プレビュー | Microsoft Docs"
description: "Intune Azure プレビュー: iOS デバイスで電子メール接続を構成するために使用できる Intune 設定について説明します。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f16c9dfb41cb2cfe07ce473a131dac767dee9c74
ms.openlocfilehash: 255a5e8c8b430e15aba989e1ce805f7d627f0e0c


---

# <a name="email-profile-settings-for-ios-devices-in-intune-azure-preview"></a>Intune Azure プレビューでの iOS デバイス向けの電子メール プロファイル設定

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **[電子メール サーバー]** - Exchange サーバーのホスト名。
- **[アカウント名]** - ユーザーのデバイスに表示される電子メール アカウントの表示名。
- **[AAD からのユーザー名の属性]** - この電子メール プロファイルのユーザー名を生成するために使用される Active Directory (AD) または Azure AD の属性です。 **プライマリ SMTP アドレス** (**user1@contoso.com** など) または**ユーザー プリンシパル名** (**user1**、**user1@contoso.com** など) を選択します。
- **[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。 Exchange へのログインにプライマリ SMTP アドレスを使用する場合は **[プライマリ SMTP アドレス]** を選択し、完全プリンシパル名を電子メール アドレスとして使用する場合は **[ユーザー プリンシパル名]** を使用します。
- **[認証方法]** - 電子メール プロファイルで使用する認証方法として、**[ユーザー名とパスワード]** または **[証明書]** を選択します。
    - **[証明書]** を選択した場合は、Exchange 接続の認証に使用するために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。
- **[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。
- **[S/MIME]** - S/MIME 暗号化を使用して電子メールを送信します。
    - **[証明書]** を選択した場合は、Exchange 接続の認証に使用するために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。
- **[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。
- **[他の電子メール アカウントにメッセージを移動することを許可する]** - デバイスで構成されている複数のアカウント間で、ユーザーが電子メール メッセージを移動できるようにします。
- **[サード パーティ アプリケーションから電子メールを送信できるようにする]** - 電子メールを送信するための既定のアカウントとしてこのプロファイルを選択することをユーザーに許可し、(たとえば、ファイルを電子メールに添付する目的で) ネイティブの電子メール アプリで電子メールを開くことをサードパーティ製アプリに許可します。
- **[最近使用した電子メール アドレスを同期する]** - この機能を使用すると、ユーザーは、デバイスで最近使用された電子メール アドレスのリストをサーバーと同期できるようになります。



<!--HONumber=Feb17_HO1-->

