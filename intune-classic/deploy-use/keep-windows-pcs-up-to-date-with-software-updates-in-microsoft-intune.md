---
title: "Windows PC のソフトウェア更新プログラム"
description: "Intune で最新の修正プログラムとソフトウェア更新プログラムを迅速にインストールし、管理対象のコンピューターを最新の状態に保つ。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 48e9c41a-d2de-424e-9610-cfd1ad514210
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1243d52f3d135ac02b9451022451bf9cf8c7304b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2017
---
# <a name="keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune"></a>Microsoft Intune でソフトウェア更新プログラムを使用して Windows PC を最新の状態に保つ

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune は、さまざまな方法で管理対象コンピューターをセキュリティで保護します。たとえば、ソフトウェア更新プログラムの管理機能では、最新の修正プログラムやソフトウェア更新プログラムを迅速にインストールして、コンピューターを最新の状態に保ちます。

まだ Intune クライアントをコンピューターにインストールしていない場合は、「[Microsoft Intune を使用して Windows PC クライアントをインストールする](install-the-windows-pc-client-with-microsoft-intune.md)」を参照してください。

管理対象コンピューターに適用できる新しい更新プログラムが Microsoft Update で提供されたり、サード パーティ製更新プログラムが作成されたりすると、**[更新プログラム]** ワークスペースの **[概要]** ページに通知が表示されます。 この通知リンクを選択すると、更新プログラムに関する詳細情報の表示、更新プログラムの承認または却下、承認した場合に更新プログラムをインストールするコンピューターの表示など、さまざまな操作を実行できます。

> [!IMPORTANT]
> クライアントをインストールして少なくとも 1 つのコンピューター クライアントを正常に管理するまで、 **[更新プログラム]** ワークスペースは管理コンソールに表示されません。

更新プログラムが承認されてインストールされると、Intune コンソールの **[更新プログラム]** ワークスペースで、インストールが成功したか失敗したかを確認できます。

次のセクションでは、管理対象コンピューターのソフトウェアを最新の状態に保つ方法について説明します。

## <a name="before-you-start"></a>アップグレードを開始する前に
ソフトウェアの更新プログラムを作成して承認する前に、更新プログラムをインストールする時間と方法を制御するポリシーを構成して、使用するコンピューターに展開します。

### <a name="to-configure-update-policy-settings"></a>更新ポリシー設定を構成するには

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[ポリシー]** &gt; **[概要]** &gt; **[ポリシーの追加]** の順に選択します。

2.  更新設定の **Microsoft Intune エージェントの設定** ポリシーを構成して展開します。 推奨される設定を使用することも、設定をカスタマイズすることもできます。 ポリシーの作成および展開方法の詳細については、「[Microsoft Intune コンピューター クライアントを使用した一般的な Windows PC 管理タスク](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)」を参照してください。

次の表に、ポリシーに構成できる値と、ポリシーをカスタマイズしない場合に使用される推奨値を示します。 これらの設定は、[ **更新プログラム** ] セクションに表示されます。

  |ポリシー設定|説明|
    |------------------|--------------------|
    |**更新プログラムおよびアプリケーションの自動検出頻度 (時間)** |Intune で新しい更新プログラムとアプリケーションをチェックする頻度 (8 ～ 22 時間) を指定します。<br /><br />推奨値: **8** 時間。|
    |**更新プログラムおよびアプリケーションの自動インストールまたはメッセージを表示** |更新プログラムが自動的にインストールされるようにするか、インストールする前にユーザーに確認するメッセージを表示するかを指定します。 また、更新プログラムとアプリケーションのインストールのスケジュールも指定できます。<br /><br />**更新プログラムおよびアプリケーションをスケジュールどおりインストールする**: 指定したスケジュールに従って、更新プログラムとアプリケーションをインストールします。<br /><br />依存するポリシー設定として、 **[Windows コンピューターの自動メンテナンスを利用する]**  で、Windows 自動メンテナンス期間中に更新プログラムとアプリケーションをインストールすることを指定します。<br /><br />**ユーザーにインストールの確認メッセージを表示する**: 更新プログラムをインストールする準備ができるとユーザーにメッセージが表示されます。<br /><br />推奨値:<br /><br />**更新プログラムおよびアプリケーションをスケジュールどおりインストールする**: オン<br /><br />**スケジュールされた日: 毎日**<br /><br />**スケジュールされた時刻: 午前 3:00**<br /><br />**Windows コンピューターの自動メンテナンスを利用する**: オン|
    |**Windows を中断しない更新プログラムを直ちにインストールする** |**[許可する]** に設定すると、Windows を中断または再起動する更新プログラムを除き、ダウンロードされた更新プログラムが直ちにインストールされます。 [ **更新プログラムの自動インストールまたはメッセージを表示** ] 設定の構成に従って更新プログラムがインストールされます。<br /><br />**[許可しない]** に設定すると、**[更新プログラムの自動インストールまたはメッセージを表示]** 設定の構成に従って更新プログラムがインストールされます。<br /><br />推奨値: **Allow** |
    |**スケジュールされた更新プログラムおよびアプリケーションがインストールされた後で Windows が再起動されるまでの待ち時間 (分)** |スケジュールされた更新プログラムとアプリケーションのインストール後に、Windows を再起動するまでの時間 (1 ～ 30 分) を指定します。<br /><br />推奨値: **15 ?** |
    |**更新プログラムおよびアプリケーションのスケジュールされたインストールが実行されなかった場合に、Windows の再起動後インストールを再開するまでの待ち時間 (分)** |スケジュールされた更新が実行されなかったときに、Windows の再起動後に、更新プログラムとアプリケーションのインストールを開始するまでの時間 (1 ～ 60 分) を指定します。<br /><br />推奨値: **5 分**|
    |**スケジュールされた更新プログラムおよびアプリケーションのインストール後の Windows の再起動を、ログオンしているユーザーが制御できるようにする** |ログオンしたユーザーが Windows の再起動を延期できる (**[はい]** に設定した場合) か、Windows の自動再起動を通知する (**[いいえ]** に設定した場合) かを指定します。 更新プログラムとアプリケーションのスケジュールされたインストールが完了したときに、ログオンしているユーザーがいない場合は、必要に応じて Windows が自動的に再起動されます。 " **いいえ**" に設定した場合、既定では、Windows が再起動されるまでの時間が 5 分に設定されます。<br /><br />推奨値: **○**|
    |**Intune クライアント エージェントの必須の更新プログラムで Windows の再起動の確認メッセージを表示する** |Intune クライアントの必須の更新プログラムで Windows の再起動が必要な場合に、ログオンしたユーザーに Windows の再起動を確認するかどうかを指定します。<br /><br />推奨値: **○**|
    |**Microsoft Intune クライアント エージェントの必須更新プログラムのインストール スケジュール** |クライアントの更新プログラムのインストールを実行する時間をスケジュールします。<br /><br />推奨値: 未構成|
    |**スケジュールされた更新プログラムおよびアプリケーションのインストール後に Windows の再起動を促すメッセージが表示されるまでの待ち時間 (分)** |Windows の再起動が必要な更新プログラムまたはアプリケーションがスケジュールどおりインストールされ、ユーザーが再起動を延期した場合に、Windows の再起動を促すメッセージを表示する間隔 (1 ～ 1440 分) を指定します。<br /><br />推奨値: **30 分** |

## <a name="update-software-made-by-microsoft"></a>Microsoft のソフトウェアの更新
Microsoft のソフトウェアの更新は非常に簡単です。 ただし、開始する前に、構成しておく必要がある項目が 2 つあります。

-   **製品カテゴリと更新プログラムの分類** – コンピューターで使用できるようにする更新プログラムのカテゴリと分類を定義します。 たとえば、Microsoft Office の重要な更新プログラムだけをインストールするように設定できます。

-   **自動承認規則** - これらの規則は、指定した種類の更新を自動的に承認し、管理のオーバーヘッドを減らします。 たとえば、すべての重要なソフトウェアの更新プログラムを自動的に承認できます。

次の 2 つの手順に従って、ソフトウェアの更新プログラムを使用する準備を行います。

### <a name="configure-the-product-categories-and-update-classifications-you-want-to-make-available-to-managed-computers"></a>管理対象コンピューターで利用できるようにする製品カテゴリと更新プログラムの分類を構成する

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[管理者]** &gt; **[更新プログラム]** の順に選択します。

2.  **[サービスの設定:更新]** ページの **[製品カテゴリ]** 一覧で、コンピューターで使用可能にする更新プログラムのカテゴリを選択します。 最も一般的な更新プログラムは、既定で選択されていることに注意してください。

    > [!IMPORTANT]
    > コンピューターが管理者によって承認された更新プログラムを受け取れるように、Windows Server Update Services (WSUS) の **[イントラネットの Microsoft 更新サービスの場所を指定する]** というグループ ポリシー設定は Intune に登録されているコンピューターに適用しないでください。

3.  [ **更新プログラムの分類** ] 一覧で、管理対象コンピューターで利用できるようにする更新プログラムのクラスを選択します。 ここでも、最も一般的な更新プログラムは既定で選択されます。

4.  **[保存]** を選択して、選択内容を保存します。

### <a name="to-configure-automatic-approval-rules-for-software-updates"></a>ソフトウェアの更新プログラムの自動承認規則を構成するには

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[管理者]** &gt; **[更新プログラム]** の順に選択します。

2.  **[サーバー設定: 更新]** ページの **[自動承認規則]** セクションで、**[新規]** を選択します。

3.  自動承認規則の作成ウィザードの **[全般]** ページで、規則の名前と、必要に応じて説明を入力します。

4.  **[製品カテゴリ]** ページで、更新プログラムを自動的に承認する製品を選択します。

5.  **[更新プログラムの分類]** ページで、自動的に承認されるようにする更新プログラムの分類を指定します。

6.  **[展開]** ページで、次の操作を行います。

    -   新しい規則を展開するコンピューター グループを選択してから、**[追加]** を選択します。

    -   更新プログラムのインストールの期限を指定するには、 **[これらの更新プログラムのインストール期限を適用します]** チェック ボックスをオンにして、 **[インストールの期限]** 一覧で、インストールの期限を選択します。

        > [!NOTE]
        > インストールの期限を指定した場合、その期限が過ぎた後は、管理対象コンピューターを 1 回または数回再起動しなければならないことがあります。

    -   終了したら、**[次へ]** を選択します。

7.  **[概要]** ページで、新しい規則の設定を確認してから **[完了]** を選択します。

**[サービスの設定: 更新]** ページの **[自動承認規則]** セクションに、新しい規則が表示されます。

> [!NOTE]
> 新しく作成した自動承認規則で承認されるのは、今後リリースされる更新プログラムのみです。Intune に既に存在する更新プログラムは自動的に承認されません。 これらの更新プログラムを承認するには、自動承認規則を実行する必要があります。


### <a name="to-edit-run-or-delete-an-automatically-approved-update-rule"></a>更新プログラムの自動承認規則を編集、実行、または削除するには

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[管理者]** &gt; **[更新プログラム]** の順に選択します。

2.  **[自動承認規則]** セクションで、規則を選択して、次のいずれかの操作を実行します。

    -   規則を編集するには、**[編集]** をクリックし、**自動承認規則の更新ウィザード**で規則のパラメーターを変更します。

    -   規則を実行するには、**[選択項目の実行]** を選択します。

    -   規則を削除するには、**[削除]** を選択します。

        > [!NOTE]
        > 削除した規則で既に承認されている更新プログラムには影響しません。

## <a name="update-software-not-made-by-microsoft"></a>Microsoft 以外のソフトウェアの更新
Microsoft 以外のソフトウェアの更新プログラムを展開できます。 この操作には、 **更新プログラムのアップロード** ウィザードを使用して、クラウドの記憶域に更新プログラムをアップロードします。これで、Microsoft のソフトウェアと同じように更新プログラムを承認または却下できます。

### <a name="to-upload-and-configure-a-third-party-update"></a>サード パーティの更新プログラムをアップロードして構成するには

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[更新プログラム]** &gt; **[概要]** &gt; **[アップロード]** の順に選択します。

2.  **[更新ファイル]** ページで **[参照]** を選択し、更新プログラム パッケージをインストールするのに必要なセットアップ ファイルを選択します。 たとえば、Windows インストーラー (.msi) ファイル、Windows インストーラー修正プログラム (.msp) ファイル、.exe プログラム ファイルなどがあります。 セットアップ ファイルと同じフォルダーにある追加のファイルまたはフォルダーを含めることもできます。

    アップロードするファイルの合計サイズが表示されます。 このサイズは、インストール ファイルの圧縮解除後のサイズではないことに注意してください。

3.  セットアップ ファイルを指定したら、**[更新プログラムの説明]** ページに、Intune によってソフトウェア セットアップ ファイルから抽出されたソフトウェアの名前、説明、および分類の情報が表示されます。 展開する更新プログラムに分類の情報を付けるには、該当する分類 (更新プログラム、重要な更新プログラム、セキュリティ更新プログラム、ロールアップ更新プログラム、Service Pack) を指定します。 完了したら、**[次へ]** を選択します。

4.  ウィザードの **[要件]** ページで、この更新プログラムを適用可能にする管理対象コンピューターのアーキテクチャ (32-bit、64-bit、またはその両方) とオペレーティング システムを選択します。

5.  **[検出規則]** ページで、管理対象コンピューターに更新プログラムが既に存在するかどうかを Intune で判別する方法を指定します。 既定のオプション **[既定の検出規則を使用する]** を使用すると、Intune は常に、インストール先の各コンピューターに 1 回ずつ更新プログラム パッケージをインストールします。

    > [!NOTE]
    > 指定したセットアップ ファイルが、Windows インストーラー ファイルまたは .msp ファイルの場合、ウィザードの **[検出規則]** ページは表示されません。 これは、Windows インストーラー ファイルと .msp ファイルには、インストール済みの更新プログラムを検出する独自の手順が含まれているからです。

    更新プログラムが既に管理対象コンピューターにインストールされているかどうかを判別する次の規則のうち、1 つまたは複数を選択します。

    -   **ファイルが存在します**

    -   **MSI 製品コードが存在しています**

    -   **レジストリ キーが存在しています**

6.  ファイルのパス、名前、Windows インストーラーの製品コード、レジストリ キーなどの検出規則の構成に必要な追加情報を指定し、**[次へ]** を選択します。

7.  ウィザードの **[要件]** ページで、この更新プログラムをインストールする前にインストールしておく必要があるソフトウェアを指定します。 **[なし]** を指定し、既に追加されて Intune で管理されているソフトウェア パッケージを選択するか、ソフトウェアを説明する次の規則のいずれかを指定することができます。

    -   **ファイルが存在します**

    -   **MSI 製品コードが存在しています**

    -   **レジストリ キーが存在しています**

8.  ファイルのパス、名前、Windows インストーラーの製品コード、レジストリ キーなどの検出規則の構成に必要な追加情報を指定し、**[次へ]** を選択します。

9. ウィザードの **[コマンド ライン引数]** ページで、セットアップ ファイルの動作を変更する、必要なインストール プロパティをインストール コマンド ラインに追加できます。 たとえば、一部のソフトウェアでは、サイレント インストールを有効にする **/q** プロパティをサポートしています。 サポートされるコマンド ライン引数の詳細については、ソフトウェア パッケージのドキュメントを参照してください。 必要なコマンド ライン引数を指定して、**[次へ]** を選択します。

    > [!NOTE]
    > サイレント インストールをサポートしていない更新プログラムは、Intune を使用してインストールできません。

10. ウィザードの **[リターン コード]** ページで、更新プログラムのインストールからのリターン コードの意味を指定できます。 既定では、Intune は業界標準のリターン コードを使用して、更新プログラムのパッケージがインストールされたかどうかを示します。 次のリターン コードがあります。

|リターン コード|説明|
|---------------|------------------|
|**0**|成功|
|**3010**|成功 (再起動が必要)|

11. 上記以外のリターン コードは、すべて失敗と見なしてください。
更新プログラムによっては、リターン コードの意味が業界標準とは異なることがあります。 このような場合は、独自のリターン コードの意味を指定します。

12. 必要なリターン コードを指定するか、編集して、**[次へ]** を選択します。

13. このウィザードの **[概要]** ページで、実行される操作を確認し、**[アップロード]** を選択してウィザードを完了します。

アップロードした更新プログラムは、Intune のクラウド記憶域に保管されます。 アップロードに必要な空き領域が不足している場合は、アップロードするときにメッセージが表示されます。 更新プログラムのアップロードを開始した後でないと、Intune は空き領域が十分かどうかを判断できません。これは、圧縮されたセットアップ ファイルとインストール ファイルの展開時により多くの領域が必要になるためです。

サード パーティ製の更新プログラムを Intune にアップロードすると、**[すべての更新プログラム]** ウィンドウの **[更新プログラム]** ワークスペースに表示されます。 その後で、更新プログラムを承認して展開できます。 詳細については、次の「更新プログラムの承認と拒否」セクションを参照してください。

## <a name="approve-and-decline-updates"></a>更新プログラムの承認と拒否
更新プログラムをインストールする準備ができると、 **[更新プログラム]** ワークスペースの **[更新プログラムの概要]** ページにある **[更新状態]**にメッセージが表示されます。 このメッセージを選択して **[すべての更新プログラム]** ページを開き、承認の準備ができている更新プログラムを表示します。

**[フィルター]** 一覧を使用して、更新プログラムを簡単に見つけることができます。 たとえば、失敗した更新プログラムや、置き換えられた更新プログラムだけを表示できます。

一覧から更新プログラムを選択すると、次の表に示す、更新プログラムの管理に使用できるその他のコマンドが表示されます。

|作業|説明|
|--------|--------------------|
|**プロパティの表示**|適用可能なコンピューターの数など、更新プログラムに関する詳細情報を表示します。|
|**編集**|Microsoft 以外の更新プログラムにのみ使用できます。 更新プログラムのプロパティを編集できます。|
|**承認**|選択した更新プログラムを承認し、展開先のグループを構成できます。 詳細については、このトピックの「**更新プログラムを承認するには**」の手順を参照してください。|
|**拒否**|更新プログラムの以前の承認を削除し、既定の表示で更新プログラムを非表示にします。 また、更新プログラムのすべてのレポート データが削除されます。<br /><br />拒否された更新プログラムの場所を後で確認する場合は、 **[すべての更新プログラム]** ページのフィルターを **[拒否済み]**に設定します。 その後、必要に応じて、この更新プログラムを承認します。<br /><br />Microsoft Update で期限切れになったことが原因で更新プログラムが拒否された場合は、この更新プログラムを Intune 管理コンソールで承認することはできません。<br /><br />コンピューターに展開されている更新プログラムのポリシーを削除した場合は、それらの更新プログラムのポリシー設定の値が、コンピューターにインストールされているオペレーティング システムの既定の状態にリセットされます。|
|**削除**|Microsoft 以外の更新プログラムにのみ使用できます。 選択した更新プログラムを削除します。|
|**アップロード**|**更新プログラムのアップロード** ウィザードを開始し、展開する Microsoft 以外の更新プログラムをアップロードできます。|

### <a name="to-approve-updates"></a>更新プログラムを承認するには

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[更新プログラム]** &gt; **[概要]** &gt; **[承認待ちの新しい更新プログラム]** の順にクリックします。

    **[更新プログラム]** ワークスペースで、**[概要]** &gt; **[承認待ちの新しい更新プログラム]** の順に選択します。

    > [!NOTE]
    > **[更新状態]** 領域の **[承認待ちの新しい更新プログラム]** リンクは、承認する必要のある更新プログラムが少なくとも 1 つある場合だけ表示されます。

2.  更新プログラムを選択し、ページの下部に表示される更新プログラムのプロパティで、その更新プログラムが承認するものに間違いないことを確認したら、**[承認]** を選択します。 **Ctrl** キーを押しながら各項目を選択することで、複数の更新プログラムを選択できます。

3.  **[グループの選択]** ページで、更新プログラムを展開するグループを選択し、**[追加]** を選択します。 グループを指定し終わったら、**[次へ]** を選択します。

4.  **[展開アクション]** ページで、一覧のグループごとに次の操作を行います。

    -   **[承認]** 一覧で、次のいずれかを選択します。

        -   **必須のインストール** - 指定したグループ内のコンピューターに更新プログラムをインストールします。

        -   **インストールしない** - 適用できるかどうかのみをレポートし、更新プログラムをインストールしません。

        -   **利用可能なインストール** - ユーザーがポータル サイトからオン デマンドでインストールできます。

        -   **アンインストール** - 対象のグループにあるコンピューターから更新プログラムを削除します。

            > [!IMPORTANT]
            > 更新プログラムは、Intune によってインストールされなかった場合でも削除されます。

    -   **[期限]** 一覧で、次のいずれかを選択します。

        -   **なし** - 更新プログラムのインストール期限を設定しません。ユーザーは、更新プログラムのインストールを何度でも拒否することができます。

        -   **直ちに** - 対象のコンピューターに、更新プログラムがインストール可能になり次第インストールされます。

        -   **カスタム** - 承認した更新プログラムをインストールする期限の日付と時刻を指定します。

        -   **1 週間**、 **2 週間**、 **1 か月** - 更新プログラムが指定した期間内にインストールされます。

5.  設定を保存するには **[完了]** を、設定を破棄して更新プログラムの一覧に戻るには **[キャンセル]** を選択します。

    > [!IMPORTANT]
    > 更新プログラムの **[インストールしない]**、 **[必須のインストール]**、または **[アンインストール]** の設定は、子グループで明示的に構成していない限り、親グループの構成が、そのすべての子グループに継承されます。

6.  [ **すべての更新プログラム** ] ページの下端にある詳細ウィンドウで、更新プログラムに関する通知用のメッセージを確認できます。


### <a name="see-also"></a>関連項目
[Windows PC を保護するためのポリシー](policies-to-protect-windows-pcs-in-microsoft-intune.md)