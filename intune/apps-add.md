---
title: "アプリを Microsoft Intune に追加する方法"
titleSuffix: Intune on Azure
description: "この手順では、Intune にアプリを追加して、ユーザーとデバイスに割り当てられる状態にします。 &quot;"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 6b4df1ca6db5ce733ab7dab4e715ab0850dd7c8b
ms.contentlocale: ja-jp
ms.lasthandoff: 06/08/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>アプリを Microsoft Intune に追加する方法

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

ユーザー用アプリを管理して割り当てるには、そのアプリを Intune に追加する必要があります。 Intune ではさまざまな種類のアプリがサポートされ、オプションは種類ごとに異なる可能性があります。

Intune では、以下の種類のアプリを追加して割り当てることができます。

![Intune でサポートされているアプリの種類](./media/app-types.png)

次のプラットフォームがサポートされます。

- Android ストア アプリ
- Android 基幹業務 (LOB) アプリ
- iOS ストア アプリ
- iOS 基幹業務 (LOB) アプリ
- Web アプリ
- Windows Phone 8.1 ストア アプリ
- Windows Phone 基幹業務アプリ (.xap ファイル)
- Windows ストア アプリ
- Windows 基幹業務アプリ (.msi ファイルのみ)

>[!TIP]
> 基幹業務 (LOB) アプリは、アプリ ストアからではなく、アプリのインストール ファイルからインストールするアプリです。 たとえば、iOS LOB アプリをインストールするには、アプリケーションのアーカイブ ファイル (拡張子 .ipa) を追加します。 これらは通常、社内で作成したアプリです。

## <a name="before-you-start"></a>アップグレードを開始する前に

アプリの追加と割り当てを始める前に、次の点を検討してください。

- ストアからアプリを追加して割り当てる場合、エンド ユーザーがそのアプリをインストールするには、そのストアのアカウントをエンド ユーザーが用意する必要があります。
- 割り当てるアプリまたは項目は、組み込みの iOS アプリに依存する場合があります。 たとえば、iOS ストアからブックを割り当てる場合は、デバイス上に iBooks アプリが存在する必要があります。 iBooks の組み込みアプリを削除した場合は、Intune を使用してそれを元に戻すことはできません。

## <a name="cloud-storage-space"></a>クラウドの記憶域の容量
ソフトウェア インストーラーのインストールの種類を使用して作成したすべてのアプリ (たとえば、基幹業務アプリ) は、パッケージ化され、Intune クラウドの記憶域にアップロードされます。 Intune の試用版サブスクリプションでは、管理対象のアプリと更新プログラムの保管用として、2 ギガバイト (GB) 分のクラウドの記憶域を使用できます。 完全版のサブスクリプションには、20 GB の記憶領域が含まれています。

Intune の追加ストレージは、当初の購入方法を使用して購入できます。  請求書やクレジット カードでお支払いの場合は、[サブスクリプション管理ポータル](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions)をご覧ください。  それ以外の場合は、パートナーまたは営業担当者にお問い合わせください。

クラウドの記憶域の容量の要件は次のとおりです。

-   すべてのアプリのインストール ファイルは、同じフォルダーにある必要がある。
-   アップロードするファイルの最大ファイルサイズは 2 GB。

## <a name="how-to-create-and-edit-categories-for-apps"></a>アプリのカテゴリを作成して編集する方法

エンド ユーザーが会社のポータルでアプリを見つけやすいように、そのアプリはカテゴリを使って並べ替えることができます。 アプリには、**デベロッパー アプリ**、**通信アプリ**など、1 つ以上のカテゴリを割り当てることができます。
アプリを Intune に追加するときに、必要なカテゴリを選択するためのオプションが表示されます。 プラットフォーム固有のトピックを使用してアプリを追加し、カテゴリを割り当てます。 独自のカテゴリを作成して編集するには、次の手順を実行します。

1. Azure ポータルにサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[モバイル アプリ]** を選択します。
4. **[モバイル アプリ]** ワークロードで、**[セットアップ]** > **[アプリのカテゴリ]** の順に選択します。
5. **[アプリのカテゴリ]** ブレードで、現在のカテゴリの一覧が表示されます。 次の操作のいずれかを選択します。
    - **[カテゴリの作成]** - **[Create category (カテゴリの作成)]** ブレードで、新しいカテゴリの名前を入力します。 名前を入力できる言語は 1 つのみです。Intune では翻訳されません。 完了したら [**作成**] をクリックします。
    - **[カテゴリの編集]** - 一覧の任意のカテゴリについては、"**...**" を選択します。 **[プロパティ]** ブレードで、カテゴリの新しい名前を入力するか、カテゴリを削除できます。


## <a name="apps-added-automatically-by-intune"></a>Intune によって自動的に追加されるアプリ

マイクロソフトによって発行された次のアプリは、Intune に組み込まれており、割り当てられる状態になっています。

|||
|-|-|
|名前|プラットフォーム|アプリの種類|
|Azure Information Protection|Android|管理対象の Android ストア アプリ|
|携帯端末用 Dynamics CRM|Android|管理対象の Android ストア アプリ|
|タブレット PC 用 Dynamics CRM|Android|管理対象の Android ストア アプリ|
|Excel|iOS|管理対象の iOS ストア アプリ|
|Excel|Android|管理対象の Android ストア アプリ|
|Managed Browser|Android|管理対象の Android ストア アプリ|
|Managed Browser|iOS|管理対象の iOS ストア アプリ|
|携帯端末の Microsoft Dynamics CRM|iOS|管理対象の iOS ストア アプリ|
|タブレット PC の Microsoft Dynamics CRM|iOS|管理対象の iOS ストア アプリ|
|Microsoft Power BI|iOS|管理対象の iOS ストア アプリ|
|Microsoft Power BI|Android|管理対象の Android ストア アプリ|
|Microsoft SharePoint|iOS|管理対象の iOS ストア アプリ|
|Microsoft SharePoint|Android|管理対象の Android ストア アプリ|
|Microsoft Teams|Android|管理対象の Android ストア アプリ|
|Microsoft Teams|iOS|管理対象の iOS ストア アプリ|
|OneDrive|iOS|管理対象の iOS ストア アプリ|
|OneDrive|Android|管理対象の Android ストア アプリ|
|OneNote|iOS|管理対象の iOS ストア アプリ|
|Outlook|Android|管理対象の Android ストア アプリ|
|Outlook|iOS|管理対象の iOS ストア アプリ|
|Outlook グループ|Android|管理対象の Android ストア アプリ|
|Outlook グループ|iOS|管理対象の iOS ストア アプリ|
|PowerPoint|iOS|管理対象の iOS ストア アプリ|

## <a name="next-steps"></a>次の手順

次のトピックのいずれかを選択して、各プラットフォーム用のアプリを Intune に追加する方法を確認してください。

- [Android ストア アプリ](store-apps-android.md)
- [Android LOB アプリ](lob-apps-android.md)
- [iOS ストア アプリ](store-apps-ios.md)
- [iOS LOB アプリ](lob-apps-ios.md)
- [Web アプリ (すべてのプラットフォーム)](web-app.md)
- [Windows Phone 8.1 ストア アプリ](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB アプリ](lob-apps-windows-phone.md)
- [Windows ストア アプリ](store-apps-windows.md)
- [Windows LOB アプリ](lob-apps-windows.md)
