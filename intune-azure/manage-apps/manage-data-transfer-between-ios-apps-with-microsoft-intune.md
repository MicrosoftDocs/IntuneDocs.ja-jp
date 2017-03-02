---
title: "iOS アプリ間のデータ転送を管理する | Intune Azure プレビュー | Microsoft Docs"
description: "Intune Azure プレビュー: このトピックを使用すると、iOS の開く機能とモバイル アプリ管理ポリシーを使用してアプリ間のデータ転送を管理する方法を把握できます。"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>iOS アプリ間のデータ転送を管理する方法 
## <a name="manage-ios-apps"></a>iOS アプリを管理する
会社データの保護には、ファイル転送を管理対象のアプリに限定する処理も含まれます。  iOS アプリは次の方法で管理できます。

-   アプリ (**ポリシーで管理されている**アプリと呼ばれます) のアプリ保護ポリシーを構成して、会社データの損失を回避します。

-   また、アプリは **MDM チャネル**から展開して管理することもできます。  これには、デバイスが MDM ソリューションに登録されていることが必要です。 これらは**ポリシーで管理されている**アプリであるか、またはその他の管理対象アプリである必要があります。

iOS デバイスの **Open In Management** 機能を使用すると、**MDM チャネル**を使用して展開されているアプリ間でのみファイル転送が行われるよう制限できます。 Open In Management の制限は、構成設定で設定され、MDM ソリューションを使用して展開されます。  展開されているアプリをユーザーがインストールすると、管理者が設定した制限が適用されます。
##  <a name="using-app-protection-with-ios-apps"></a>iOS アプリでのアプリ保護の使用
アプリ保護ポリシーは、iOS の **Open in Management** 機能と共に使用して、以下のように会社データを保護できます。

-   **MDM ソリューションで管理されていない従業員所有のデバイス:** アプリ保護ポリシー設定を **[Allow app to transfer data to only managed apps (アプリで管理対象アプリへのデータ転送のみ許可する)]** に設定できます。 保護されたファイルをポリシーで管理されていないアプリでアプリで開くと、エンドユーザーはファイルを読み取れません。

-   **Intune で管理されているデバイス:** Intune で登録したデバイスの場合、アプリ保護ポリシーを使用するアプリと、Intune で展開された管理対象の他の iOS アプリの間で自動的にデータを転送できるようになります。 アプリ保護ポリシーを使用するアプリ間でデータを転送できるようにするには、**[Allow app to transfer data to only managed apps (アプリで管理対象アプリへのデータ転送のみ許可する)]** 設定を有効にします。 **Open in Management** 機能を使用して、Intune で展開されているアプリ間のデータ転送を制御できます。   

-   **サード パーティの MDM ソリューションで管理されているデバイス:** iOS の **Open In Management** 機能を使用して、データ転送が管理対象のアプリに対してのみ行われるよう制限できます。
サードパーティの MDM ソリューションを使用して展開するアプリを、Intune で構成したアプリ保護ポリシーとも関連付けるには、[ユーザー UPN 設定の構成](#configure-user-upn-setting)チュートリアルに従ってユーザー UPN 設定を構成する必要があります。  アプリがユーザー UPN 設定を使用して展開されている場合、エンド ユーザーが職場アカウントを使用してサインインすると、アプリ保護ポリシーがアプリに適用されます。

> [!IMPORTANT]
> ユーザー UPN 設定は、サード パーティの MDM によって管理されるデバイスに展開されたアプリに対してのみ必要です。  Intune の管理対象デバイスの場合は、この設定は必要ありません。

## <a name="configure-user-upn-setting"></a>ユーザー UPN 設定を構成する
この構成は、サード パーティの MDM ソリューションによって管理されているデバイスに必要となります。 以下に示す手順では、UPN 設定の一般的な実装方法と、その結果として得られるのエンドユーザー エクスペリエンスを示しています。


1.  Azure ポータルで、iOS プラットフォームの[モバイル アプリ管理ポリシーを構成します](app-protection-policies.md)。 企業の要件に合わせてポリシー設定を構成し、このポリシーを使用するアプリを選択します。

2.  手順 3 と 4 で説明した設定を使用して、**サードパーティの MDM ソリューションで**管理するアプリと電子メール プロファイルを展開します。

3.  key=IntuneMAMUPN, Value=<username@company.com> [例: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Open In Management ポリシーを登録済みデバイスに展開します。

### <a name="example-end-user-experience"></a>エンド ユーザー エクスペリエンスの例

1.  エンド ユーザーは、デバイスに Microsoft Word アプリをインストールします。

2.  エンド ユーザーが管理対象のネイティブ メール アプリを起動して、自分の電子メールにアクセスします。

3.  エンド ユーザーがネイティブ メールから Microsoft Word でドキュメントを開こうとします。

4.  Word アプリが起動するとき、エンド ユーザーは職場アカウントを使用してログインするよう求められます。  プロンプトが表示されたときにエンド ユーザーが入力するこの職場アカウントは、Microsoft Word アプリのアプリ構成設定で構成し、指定したアカウントと一致する必要があります。

    > [!NOTE]
    > エンド ユーザーは、私用で Word アプリを使用するときに、個人の作業に使用し、アプリ保護ポリシーの影響を受けない個人アカウントを Word に追加することができます。

5.  ログインが成功すると、アプリのポリシー設定が Word アプリに適用されます。

6.  これでデータ転送が成功し、ドキュメントにはアプリで企業 ID のタグが付けられます。 また、データが作業コンテキスト内で処理されるときには、ポリシー設定が適切に適用されます。

### <a name="see-also"></a>関連項目
[Intune アプリ保護ポリシーとは](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->

