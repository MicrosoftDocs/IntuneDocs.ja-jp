---
title: Microsoft Intune での Android エンタープライズ デバイスの設定 - Azure | Microsoft Docs
description: Android エンタープライズ デバイスまたは Android for Work デバイスで、デバイスでの設定を制限します。これには、コピーと貼り付け、通知の表示、アプリのアクセス許可、データの共有、パスワードの長さ、サインイン エラー、指紋によるロック解除、パスワードの再利用、勤務先の連絡先の Bluetooth 共有の有効化が含まれます。 1 つまたは複数のアプリを実行する専用のデバイス キオスクとして、デバイスを構成します。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d1d83a77d8823a05accaf1c88b57f6e380636469
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585381"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune を使用して機能を許可または制限するように Android エンタープライズ デバイスを設定する

この記事では、Android エンタープライズ デバイスで制御できるさまざまな設定の一覧を示して説明します。 モバイル デバイス管理 (MDM) ソリューションの一部として、これらの設定を使って、機能の許可または無効化、専用デバイスでのアプリの実行、セキュリティの管理などを行います。

## <a name="before-you-begin"></a>始める前に

[デバイス構成プロファイルを作成します](device-restrictions-configure.md)。

## <a name="device-owner-only"></a>デバイスの所有者のみ

### <a name="general-settings"></a>全般設定

- **[画面の取り込み]** : **[ブロック]** を選択すると、デバイス上でスクリーンショットまたは画面の取り込みを実行できなくなります。 セキュリティで保護されたビデオ出力を持たないディスプレイ デバイスにもコンテンツが表示されないようになります。 **[未構成]** を選択すると、ユーザーが画面のコンテンツを画像としてキャプチャできるようになります。
- **[カメラ]** : **[ブロック]** を選択すると、デバイス上のカメラにアクセスできなくなります。 **[必要なし]** を選択すると、デバイスのカメラへのアクセスが許可されます。
- **[既定のアクセス許可ポリシー]** : この設定は、ランタイムのアクセス許可の要求に対する既定のアクセス許可ポリシーを定義します。 指定できる値は次のとおりです。
  - **[Device default]\(デバイスの既定\)** : デバイスの既定の設定を使用します。
  - **[プロンプト]** : ユーザーは、アクセス許可を承認するように求められます。
  - **[自動許可]** : アクセス許可が自動的に付与されます。
  - **[自動拒否]** : アクセス許可が自動的に拒否されます。
- **[日付と時刻の変更]** : **[ブロック]** を選択すると、ユーザーが手動で日付と時刻を設定できなくなります。 **[未構成]** では、ユーザーがデバイス上で日付と時刻を設定できるようになります。
- **[ボリュームの変更]** : **[ブロック]** を選択すると、ユーザーがデバイスのボリュームを変更できなくなります。 **[未構成]** では、デバイスで音量設定を使用できるようになります。
- **[出荷時の設定にリセット]** : **[ブロック]** を選択すると、ユーザーがデバイスの設定で出荷時の設定にリセットするオプションを使用できなくなります。 **[未構成]** では、ユーザーがデバイス上でこの設定を使用できるようになります。
- **[Safe boot]\(セーフ ブート\)** : **[ブロック]** を選択すると、ユーザーがデバイスをセーフ モードで再起動できなくなります。 **[未構成]** では、ユーザーがデバイスをセーフ モードで再起動できるようになります。
- **[ステータス バー]** : **[ブロック]** を選択すると、通知やクイック設定を含むステータス バーにアクセスできなくなります。 **[未構成]** では、ユーザーがステータス バーにアクセスできるようになります。
- **[データ サービスのローミング]** : **[ブロック]** を選択すると、携帯ネットワーク上でのデータ ローミングが禁止されます。 **[未構成]** では、デバイスが携帯ネットワーク上にある場合はデータ ローミングを使用できるようになります。
- **[Wi-Fi 設定の変更]** : **[ブロック]** を選択すると、デバイスの所有者が作成した Wi-Fi 設定をユーザーが変更できなくなります。 ユーザーは、独自の Wi-Fi 構成を作成できます。 **[未構成]** では、ユーザーがデバイス上で Wi-Fi 設定を変更できるようになります。
- **[Wi-Fi アクセス ポイントの構成]** : **[ブロック]** を選択すると、ユーザーが Wi-Fi 構成を作成したり変更したりできなくなります。 **[未構成]** では、ユーザーがデバイス上で Wi-Fi 設定を変更できるようになります。
- **Bluetooth の構成**: **[ブロック]** を選択すると、ユーザーがデバイス上で Bluetooth を構成できなくなります。 **[未構成]** では、デバイス上で Bluetooth を使用できるようになります。
- **[テザリングおよびホットスポットへのアクセス]** : **[ブロック]** を選択すると、テザリングしたりポータブル ホットスポットにアクセスしたりできなくなります。 **[未構成]** では、テザリングしたりポータブル ホットスポットにアクセスしたりできるようになります。
- **[USB ストレージ]** : **[許可]** を選択すると、デバイス上で USB ストレージにアクセスできるようになります。 **[未構成]** では、USB ストレージにアクセスできなくなります。
- **[USB ファイルの転送]** : **[ブロック]** を選択すると、USB 経由でファイルを転送できなくなります。 **[未構成]** では、ファイルを転送できるようになります。
- **[外部メディア]** : **[ブロック]** を選択すると、デバイス上であらゆる外部メディアの使用または接続が禁止されます。 **[未構成]** では、デバイス上で外部メディアが許可されます。
- **[NFC を使用してビームでデータを転送]** : **[ブロック]** を選択すると、近距離無線通信 (NFC) テクノロジを使用してアプリからビームでデータを転送できなくなります。 **[未構成]** では、NFC を使用してデバイス間でデータを共有できるようになります。
- **[デバッグ機能]** : **[許可]** を選択すると、ユーザーがデバイス上でデバッグ機能を使用できるようになります。 **[未構成]** では、ユーザーがデバイス上でデバッグ機能を使用できなくなります。
- **[マイクの調整]** : **[ブロック]** を選択すると、ユーザーがマイクのミュートを解除したり、マイクのボリュームを調整したりできなくなります。 **[未構成]** では、ユーザーがデバイス上でマイクのボリュームを使用したり調整したりできるようになります。
- **[工場出荷時の設定へのリセット防止のためのメール アドレス]** : **[Google アカウントのメール アドレス]** を選択します。 ワイプ後にデバイスのロックを解除できるデバイス管理者のメール アドレスを入力します。 複数のメール アドレスはセミコロンで区切ります (例: `admin1@gmail.com;admin2@gmail.com`)。 メール アドレスを入力しない場合は、デバイスが出荷時の設定に復元された後にだれでもロック解除できます。 これらの電子メールは、[回復] メニューを使用して出荷時の設定へのリセットを実行するなど、非ユーザーファクトリのリセットが実行された場合にのみ適用されます。
- **[ネットワーク脱出ハッチ]** : **[有効化]** を選択すると、ユーザーがネットワーク脱出ハッチ機能をオンにできるようになります。 デバイスのブート時にネットワークに接続できない場合、脱出ハッチは一時的にネットワークに接続してデバイス ポリシーを更新するよう求めます。 ポリシーが適用されると、一時的なネットワークの情報は消去され、デバイスのブートが続行します。 この機能では次の場合にデバイスがネットワークに接続されます。
  - 前回のポリシー内に適切なネットワークがない。
  - デバイスがアプリにロック タスク モードでブートする。
  - ユーザーがデバイスの設定にアクセスできない。

  **[未構成]** では、ユーザーがデバイス上でネットワーク脱出ハッチ機能をオンにできなくなります。

- **[システムの更新プログラム]** : デバイスによる無線更新プログラムの処理方法を定義するオプションを選択します。
  - **[Device Default]\(デバイスの既定\)** : デバイスの既定の設定を使用します。
  - **[自動]** : ユーザー操作を必要とせずに、更新プログラムが自動的にインストールされます。 このポリシーを設定すると、任意の保留中の更新プログラムがすぐにインストールされます。
  - **[延期]** : 更新は 30 日間延期されます。 30 日間の終了時に、ユーザーは Android から更新プログラムをインストールするように要求されます。 デバイスの製造元または通信事業者は、重要なセキュリティ更新プログラムが延期されることを回避 (除外) することができます。 除外された更新プログラムは、デバイス上でユーザーにシステム通知が表示されます。
  - **メンテナンス ウィンドウ**: Intune で設定する毎日のメンテナンス ウィンドウで自動的に更新プログラムがインストールされます。 30 日間毎日インストールが試行されますが、スペースやバッテリー レベルが不足している場合に失敗する可能性があります。 30 日後、ユーザーは Android からインストールするように要求されます。 このウィンドウは、Play アプリの更新プログラムをインストールするためにも使用されます。 シングル アプリの専用デバイスの前景アプリが更新される可能性があるキオスクなど、専用デバイスに対してはこのオプションを使います。

- **[通知ウィンドウ]** : **[無効]** に設定すると、トースト、着信、発信、システム アラート、システム エラーなどのウィンドウ通知がデバイスに表示されなくなります。 **[未構成]** に設定すると、オペレーティング システムの既定が使用されます。これは通知の表示に使用されることがあります。
- **[最初の使用のヒントをスキップします]** : **[有効]** を選択すると、アプリからの提案を非表示またはスキップしてチュートリアルの手順を進めたり、アプリの起動時に概要のヒントを読んだりすることができます。 **[未構成]** に設定すると、オペレーティング システムの既定が使用されます。これはアプリの起動時にこのような提案の表示に使用されることがあります。

### <a name="system-security-settings"></a>システム セキュリティ設定

- **[アプリの脅威スキャン]** : **[必須]** (既定値) にすると、アプリをインストールする前およびその後に Google Play Protect によってアプリがスキャンされます。 脅威が検出されると、そのアプリをデバイスから削除するようにユーザーに警告が出される場合があります。 **[未構成]** にすると、Google Play Protect によるアプリのスキャンは有効にされず、実行されません。

### <a name="dedicated-device-settings"></a>専用デバイスの設定

これらの設定を使用して、専用デバイス上でキオスクスタイルのエクスペリエンスを構成します。 デバイスを構成して、1 つのアプリを実行させたり、複数のアプリを実行させたりすることができます。 デバイスがキオスク モードで設定されているときは、自分が追加したアプリのみを使用できます。 これらの設定は、Android エンタープライズ専用デバイスに適用されます。 Android エンタープライズのフル マネージド デバイスには適用されません。

**[キオスク モード]** : デバイスで 1 つのアプリまたは複数のアプリを実行させる場合に選択します。

- **[単一アプリ]** : ユーザーはデバイスで 1 つのアプリにのみアクセスできます。 デバイスを起動させると、特定のアプリのみが起動されます。 ユーザーは新しいアプリを開いたり、実行中のアプリを変更したりできません。

  - **[マネージド アプリを選択します]** : 一覧から Google Play のマネージド アプリを選択します。

    アプリが一覧表示されない場合は、デバイスに[いくつかの Android アプリを追加](../apps/apps-add-android-for-work.md)します。 必ず[専用デバイス用に作成したデバイス グループにアプリを割り当てます](../apps/apps-deploy.md)。

  > [!IMPORTANT]
  > シングルアプリキオスクモードを使用すると、ダイヤラーアプリが正常に機能しないことがあります。 
  
- **[複数アプリ]** : ユーザーはデバイスで限られた一連のアプリにアクセスできます。 デバイスを起動させると、ご自身で追加したアプリのみが起動されます。 ユーザーが開くことができる Web リンクをいくつか追加することもできます。 ポリシーが適用されると、ユーザーのホーム画面に許可されたアプリのアイコンが表示されます。

  > [!IMPORTANT]
  > 複数アプリの専用デバイスの場合、Google Play の [Managed Home Screen アプリ](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise)は**次を満たす必要があります**。
  >   - Intune に[クライアント アプリとして追加されている](../apps/apps-add-android-for-work.md)
  >   - 専用デバイス用に作成した[デバイス グループに割り当てられている](../apps/apps-deploy.md)
  >
  > **Managed Home Screen** アプリを構成プロファイルに含める必要はありませんが、クライアント アプリとして追加する必要があります。 **Managed Home Screen** アプリをクライアント アプリとして追加すると、構成プロファイルに追加するその他のすべてのアプリが **Managed Home Screen** アプリ上でアイコンとして表示されます。
  >
  > マルチアプリキオスクモードを使用すると、ダイヤラーアプリが正常に機能しないことがあります。 

  - **[追加]** : 一覧からアプリを選択します。

    **Managed Home Screen** アプリが一覧表示されない場合は、[これを Google Play から追加します](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise)。 必ず専用デバイス用に作成したデバイス グループに[アプリを割り当てます](../apps/apps-deploy.md)。

    また、ご自身の組織が作成したその他の [Android アプリ](../apps/apps-add-android-for-work.md)や [Web アプリ](../apps/web-app.md)をデバイスに追加することもできます。 必ず[専用デバイス用に作成したデバイス グループにアプリを割り当てます](../apps/apps-deploy.md)。

  - **仮想ホームボタン**: ユーザーを管理対象のホーム画面に表示し、ユーザーがアプリを切り替えることができるようにするソフトキーボタンです。 次のようなオプションがあります。

    - **未構成**(既定): [ホーム] ボタンが表示されません。 ユーザーは、[戻る] ボタンを使用してアプリを切り替える必要があります。
    - **スワイプ**: ホームボタンは、ユーザーがデバイスにスワイプしたときに表示されます。
    - **フローティング**: デバイス上に永続的なフローティングの [ホーム] ボタンを表示します。

  - **[キオスク モードを終了する]** : **[有効化]** を選択すると、デバイスを更新するために管理者がキオスク モードを一時停止できるようになります。 この機能を使用するには、管理者は次の操作を実行します。
  
    1. **[Exit kiosk]\(キオスクの終了\)** ボタンが表示されるまで、[戻る] ボタンを選択し続けます。 
    2. **[Exit kiosk]\(キオスクの終了\)** ボタンを選択して、 **[キオスク モードを終了するコード]** PIN を入力します。
    3. 完了したら、[管理された**ホーム画面**] アプリを選択します。 この手順により、複数アプリのキオスク モードにデバイスが再びロックされます。

      **[未構成]** に設定すると、管理者はキオスクモードを一時停止できません。 管理者が [戻る] ボタンを選択し続けて **[Exit kiosk]\(キオスクの終了\)** ボタンを選択すると、パスコードが必要であることを示すメッセージが表示されます。

    - **[キオスク モードを終了するコード]** : 4 から 6 桁の数値の PIN を入力します。 管理者はこの PIN を使って一時的にキオスク モードを停止させます。

  - **[カスタム URL の背景の設定]** : 専用デバイス上の背景画面をカスタマイズするための URL を入力します。

    > [!NOTE]
    > ほとんどの場合、少なくとも次のサイズの画像から始めることをお勧めします。
    >
    > - 電話: 1080 x 1920 ピクセル
    > - タブレット: 1920 x 1080 ピクセル
    >
    > 最適なエクスペリエンスと鮮明な詳細を目的として、デバイスごとの画像資産をディスプレイの仕様に合わせて作成することが提案されています。
    >
    > 最新のディスプレイはより高い画素密度を備え、2K/4K 相当の解像度画像を表示することができます。

  - **[Wi-fi 構成]** : **[有効]** に設定すると、管理されたホーム画面に wi-fi コントロールが表示され、エンドユーザーはデバイスを別の WiFi ネットワークに接続できます。 この機能を有効にすると、デバイスの場所もオンになります。 [未構成] (既定値) は、管理**さ**れたホーム画面に wi-fi コントロールを表示しません。 管理されたホーム画面を使用しているときに、ユーザーが Wi-fi ネットワークに接続できないようにします。

  - **[Bluetooth 構成]** : **[有効]** に管理されているホーム画面に bluetooth コントロールが表示され、エンドユーザーは bluetooth 経由でデバイスをペアリングできます。 この機能を有効にすると、デバイスの場所もオンになります。 [未構成] (既定値) は、管理**さ**れたホーム画面に Bluetooth コントロールを表示しません。 管理されたホーム画面を使用しているときに、ユーザーが Bluetooth を構成してデバイスをペアリングできないようにします。

  - **懐中電灯アクセス**: 管理されたホーム画面で懐中電灯コントロールを表示し、エンドユーザーが懐中電灯をオンまたはオフにできる**ようにし**ます。 [未構成] (既定値) は、管理**さ**れたホーム画面で懐中電灯コントロールを表示しません。 管理されたホーム画面を使用しているときに、ユーザーが懐中電灯を使用できないようにします。

  - **メディアボリュームコントロール**: **[有効]** に設定すると、管理されたホーム画面にメディアボリュームコントロールが表示され、エンドユーザーはスライダーを使用してデバイスのメディアボリュームを調整できます。 **未構成**(既定) は、管理されたホーム画面にメディアボリュームコントロールを表示しません。 ハードウェアボタンでサポートされている場合を除き、管理されたホーム画面を使用しているときに、ユーザーがデバイスのメディアボリュームを調整できないようにします。 

  - **スクリーンセーバーモード**: [**有効] に**設定すると、デバイスがロックされているか、タイムアウトになったときに、管理されたホーム画面にスクリーンセーバーが表示されます。[未構成] (既定) は、管理**さ**れたホーム画面にスクリーンセーバーを表示しません。

    有効にする場合は、次の構成も行います。

    - **カスタムスクリーンセーバーイメージの設定**: カスタムイメージの URL を入力します。 たとえば、次のように入力します。

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.html`

      URL を入力しない場合、既定のイメージがある場合は、デバイスの既定のイメージが使用されます。

    - **画面をオフにする前にデバイスがスクリーンセーバーに表示する秒数**: デバイスがスクリーンセーバーを表示する期間を選択します。 0-9999999 秒の範囲で値を入力します。 既定値は `0` 秒です。 空白のままにするか、ゼロ (`0`) に設定すると、ユーザーがデバイスと対話するまで、スクリーンセーバーはアクティブになります。
    - **[スクリーンセーバーを表示する前にデバイスが非アクティブになる秒数]** : デバイスがアイドル状態になってからスクリーンセーバーが表示されるまでの時間を選択します。 1-9999999 秒の範囲で値を入力します。 既定値は `30` 秒です。 0より大きい数値を入力する必要があります (`0`)。
    - **スクリーンセーバーを開始する前にメディアを検出**する: オーディオまたはビデオがデバイスで再生されている場合、 **[有効]** (既定値) にはスクリーンセーバーが表示されません。 [未構成] に**設定**すると、オーディオまたはビデオが再生されている場合でも、スクリーンセーバーが表示されます。

### <a name="device-password-settings"></a>デバイスのパスワード設定

- **[ロック画面を無効にする]** : **[無効化]** を選択すると、ユーザーがデバイス上でキーガードのロック画面機能を使用できなくなります。 **[未構成]** では、ユーザーがキーガード機能を使用できるようになります。
- **[無効になっているロック画面機能]** : デバイスでキーガードが有効な場合は、無効にする機能を選択します。 たとえば、 **[セキュリティで保護されたカメラ]** がオンの場合、デバイスのカメラ機能は無効になります。 オンではない機能はすべてデバイスで有効になります。

  これらの機能は、デバイスがロックされているときにユーザーが使用できます。 オンにされている機能については、ユーザーが表示したりアクセスしたりすることはありません。

- **[必要なパスワードの種類]** : デバイスに必要なパスワードの種類を定義します。 次のようなオプションがあります。
  - **デバイスの既定**
  - **パスワード必須、制限なし**
  - **脆弱な生体認証**: [強力な生体認証と脆弱な生体認証の比較](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (Android の web サイトが開きます)
  - **数値**: パスワードは `123456789` など、数値のみとする必要があります。 ユーザーが入力する必要がある**パスワードの最小文字数**を 4 から 16 文字の範囲で入力します。
  - **数値複素数**: 繰り返しや連続の番号 ("1111" や "1234" など) を使用できなくなります。 ユーザーが入力する必要がある**パスワードの最小文字数**を 4 から 16 文字の範囲で入力します。
  - **英字**: 英字の文字が必要です。 数字および記号は必要ありません。 ユーザーが入力する必要がある**パスワードの最小文字数**を 4 から 16 文字の範囲で入力します。
  - **英数字**: 大文字、英小文字、数字が含まれます。 ユーザーが入力する必要がある**パスワードの最小文字数**を 4 から 16 文字の範囲で入力します。
  - **英数字と記号**: 大文字、小文字、数字、句読点、および記号が含まれます。 次の項目も入力します。

    - **パスワードの最小文字数**: パスワードに含める必要がある最小文字数を 4 から 16 文字の範囲で入力します。
    - **必要な文字数**: パスワードに含める必要がある文字の数を 0 から 16 文字の範囲で入力します。
    - **必要な小文字の数**: パスワードに含める必要がある小文字の数を 0 から 16 文字の範囲で入力します。
    - **必要な大文字の数**: パスワードに含める必要がある大文字の数を 0 から 16 文字の範囲で入力します。
    - **必要なアルファベット以外の文字数**: パスワードに含める必要がある、アルファベット以外の文字 (アルファベット以外の任意の文字) の数を 0 から 16 文字の範囲で入力します。
    - **必要な数字の数**: パスワードに含める必要がある数字 (`1`、`2`、`3` など) の数を 0 から 16 文字の範囲で入力します。
    - **必要なシンボルの文字数**: パスワードに含める必要がある記号 (`&`、`#`、`%` など) の数を 0 から 16 文字の範囲で入力します。

- **パスワードの有効期限が切れるまでの日数**: デバイス パスワードの変更が必要になるまでの日数を 1 から 365 の範囲で入力します。 たとえば、60 日後にパスワードを変更するには、「`60`」と入力します。 パスワードの有効期限が切れると、ユーザーは新しいパスワードを作成するように求められます。
- **ユーザーがパスワードを再び使用できるようになるまでに必要なパスワード数**: 再利用できない最近のパスワードの数を 1 から 24 の範囲で入力します。 この設定を使用して、以前に使用されたことのあるパスワードの作成を制限するかどうかを指定します。
- **デバイスがワイプされるまでのサインイン失敗回数**: デバイスをワイプするまでのサインイン エラーの数を 4 から 11 の範囲で入力します。

### <a name="power-settings"></a>電源設定

- **[Time to lock screen]\(画面ロックまでの時間\)** : デバイスのロックまでに必要なアイドル時間の長さを設定します。
- **[Screen on while device plugged in]\(デバイスの接続時の画面\)** : 接続時にデバイスの画面をオンにしたままにする電源を選択します。

### <a name="users-and-accounts-settings"></a>ユーザーとアカウントの設定

- **[新規ユーザーを追加する]** : **[ブロック]** を選択すると、ユーザーが新しいユーザーを追加できなくなります。 各ユーザーは、カスタム ホーム画面、アカウント、アプリ、設定のためにデバイス上に個人用のスペースを持っています。 **[未構成]** では、ユーザーがデバイスに他のユーザーを追加できるようになります。
- **[ユーザーの削除]** : **[ブロック]** を選択すると、ユーザーの削除ができなくなります。 **[未構成]** では、ユーザーがデバイスから他のユーザーを削除できるようになります。
- **[アカウントの変更]** : **[ブロック]** を選択すると、ユーザーがアカウントを変更できなくなります。 **[未構成]** では、ユーザーがデバイス上でユーザー アカウントを更新できるようになります。

  > [!NOTE]
  > デバイスの所有者 (完全管理) デバイスでは、この設定は適用されません。 この設定を構成した場合、設定は無視され、影響はありません。

### <a name="applications"></a>アプリケーション

- **提供元不明のアプリのインストールを許可する**: **[許可]** を選択すると、ユーザーが **[不明なソース]** をオンにできるようになります。 この設定を使用すると、Google Play ストア以外のソースなど、未知のソースからアプリをインストールすることができます。 **[未構成]** では、ユーザーが **[不明なソース]** をオンにできなくなります。
- **Google Play ストア内のすべてのアプリへのアクセスを許可**: **[許可]** に設定すると、Google Play ストア内のすべてのアプリへのアクセスがユーザーに許可されます。 管理者が [クライアント アプリ](../apps/apps-add-android-for-work.md)内でブロックしているアプリにはユーザーはアクセスできません。 **[未設定]** にすると、管理者が Google Play ストアで利用できるようにしたアプリ、または[クライアント アプリ](../apps/apps-add-android-for-work.md)で必要とされるアプリのみへのアクセスがユーザーに強制されます。
- **[アプリの自動更新]** : 自動更新がインストールされている場合に選択します。 次のようなオプションがあります。
  - **未構成**
  - **ユーザー選択**
  - **しない**
  - **Wi-Fi のみ**
  - **常時**

### <a name="connectivity"></a>接続

- **常時接続 VPN**: VPN に自動的に接続および再接続するように VPN クライアントを設定するには、 **[有効化]** を選択します。 常時接続 VPN は接続されたままの状態になるか、ユーザーが自分のデバイスをロックした場合、デバイスが再起動した場合、またはワイヤレス ネットワークに変更があった場合に、すぐに接続されます。 

  すべての VPN クライアントの常時接続 VPN を無効にするには、 **[未構成]** を選択します。

  > [!IMPORTANT]
  > 1 つのデバイスには Always On VPN ポリシーを 1 つだけ展開してください。 1 つのデバイスに複数の常時接続 VPN ポリシーを展開することはサポートされていません。

- **VPN クライアント**: Always On をサポートする VPN クライアントを選択します。 次のようなオプションがあります。
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - カスタム
    - **パッケージ ID**: Google Play ストアでのアプリのパッケージ ID を入力します。 たとえば、Play ストアでのアプリの URL が `https://play.google.com/store/details?id=com.contosovpn.android.prod` の場合、パッケージ ID は `com.contosovpn.android.prod` になります。

  > [!IMPORTANT]
  > - 選択した VPN クライアントは、デバイスにインストールされている必要があり、仕事用プロファイルでアプリごとの VPN をサポートしている必要があります。 そうでない場合、エラーが発生します。 
  > - **Managed Google Play ストア**で VPN クライアント アプリを承認し、アプリを Intune に同期して、アプリをデバイスに展開する必要があります。 これを行うと、アプリがユーザーの仕事用プロファイルにインストールされます。
  > - Android 3.0.4 用の F5 Access と共にアプリごとの VPN を使用する場合、既知の問題がある可能性があります。 詳細については、[Android 3.0.4 用の F5 Access に向けた F5 のリリース ノート](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android)をご覧ください。

- **ロックダウン モード**: すべてのネットワーク トラフィックで VPN トンネルの使用を強制するには、 **[有効化]** を選択します。 VPN への接続が確立されていない場合、デバイスはネットワークにアクセスできません。

  VPN トンネルまたはモバイル ネットワークを経由したトラフィック フローを許可するには、 **[未構成]** を選択します。

- **推奨されるグローバルプロキシ**: デバイスにグローバルプロキシを追加するには、[**有効**にする] を選択します。 有効にした場合、デバイス上の一部のアプリを含む HTTP および HTTPS のトラフィックは、入力したプロキシを使用します。 このプロキシは単なる推奨事項です。 一部のアプリではプロキシを使用しない可能性があります。 **未構成**(既定) では、推奨されるグローバルプロキシは追加されません。

  この機能の詳細については、「 [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (Android サイトを開く)」を参照してください。

  有効になっている場合は、プロキシの**種類**も入力します。 次のようなオプションがあります。

  - **ダイレクト**: プロキシサーバーの詳細を手動で入力するには、このオプションを選択します。
    - **ホスト**: プロキシサーバーのホスト名または IP アドレスを入力します。 たとえば、「`proxy.contoso.com`」や「`127.0.0.1`」と入力します。
    - **[ポート番号]** : プロキシ サーバーによって使用される TCP ポート番号を入力します。 たとえば、「`8080`」と入力します。
    - **[除外するホスト]** : プロキシを使用しないホスト名または IP アドレスの一覧を入力します。 この一覧には、アスタリスク (`*`) のワイルドカードと、セミコロン (`;`) で区切られた複数のホストを含めることができます。スペースは使用できません。 たとえば、「`127.0.0.1;web.contoso.com;*.microsoft.com`」と入力します。

  - **プロキシの自動**構成: プロキシの自動構成スクリプトの**PAC URL**を入力します。 たとえば、「`https://proxy.contoso.com/proxy.pac`」と入力します。

    PAC ファイルの詳細については、「[プロキシの自動構成 (pac) ファイル](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file)(Microsoft 以外のサイトを開く)」を参照してください。

## <a name="work-profile-only"></a>仕事用プロファイルのみ

### <a name="work-profile-settings"></a>仕事用プロファイル設定

#### <a name="general"></a>全般

- **[仕事用プロファイルと個人プロファイルの間でのコピー/貼り付け]** : **[ブロック]** を選択すると、仕事用と個人用アプリの間でのコピー/貼り付けを実行できなくなります。 **[未構成]** では、ユーザーが個人プロファイル内のアプリでコピー/貼り付けを使ってデータを共有できるようになります。 
- **[仕事用プロファイルと個人プロファイル間のデータ共有]** : 仕事用プロファイル内のアプリが個人プロファイル内のアプリと共有できるようにするかどうかを選択します。 たとえば、アプリケーション内の共有アクション (Chrome ブラウザー アプリの **[Share...]\(共有...\)** オプションなど) を制御します。 この設定は、コピー/貼り付けのクリップボード動作には適用されません。 共有オプションは次のとおりです。
  - **[デバイスの既定値]** : デバイスの既定の共有動作。Android のバージョンによって異なります。 既定では、個人プロファイルから仕事用プロファイルへの共有が許可されます。 また既定では、仕事用プロファイルから個人プロファイルへの共有はブロックされます。 この設定により、仕事用プロファイルから個人プロファイルへのデータの共有が防止されます。 6\.0 以降のバージョンを実行するデバイスでは、Google によって個人プロファイルから仕事用プロファイルへのデータの共有がブロックされません。
  - **[仕事用プロファイル内のアプリで、個人プロファイルからの共有要求の処理を許可する]** : 個人プロファイルから仕事用プロファイルへの共有を許可する Android の組み込み機能を有効にします。 これを有効にすると、個人プロファイル内アプリからの共有要求を仕事用プロファイル内アプリと共有できます。 この設定は、Android 6.0 よりも前のバージョンを実行するデバイスの既定の動作です。
  - **境界を越えた共有を禁止する**: 仕事用プロファイルと個人プロファイル間の共有を防止します。
  - **共有に関する制限はありません**。双方向で仕事用プロファイルの境界を越えて共有できるようにします。 この設定を選択すると、仕事用プロファイル内のアプリと、個人プロファイル内の管理対象でないアプリとの間でデータが共有されます。 この設定により、仕事用プロファイル内の管理対象アプリがデバイスの管理対象でない側のアプリと共有されるようになります。 そのため、この設定は慎重に使用してください。

- **[デバイス ロック中の仕事用プロファイルからの通知]** : デバイスがロックされているときに、仕事用プロファイル内のアプリが通知内のデータを表示できるかどうかを制御します。 **[ブロック]** では、データが表示されなくなります。 **[未構成]** では、データが表示されます。
- **[既定のアプリのアクセス許可]** : 仕事用プロファイル内のすべてのアプリに対して既定のアクセス許可ポリシーを設定します。 Android 6 以降では、ユーザーはアプリ起動時にアプリで必要な特定のアクセス許可を付与するよう求められます。 このポリシー設定を使用すると、仕事用プロファイル内のすべてのアプリのアクセス許可をユーザーに要求するかどうかを決定できます。 たとえば、位置情報へのアクセスを必要とするアプリを、仕事用プロファイルに割り当てる場合があります。 通常、そのアプリは位置情報へのアクセスについてユーザーの承諾または拒否を求めます。 このポリシーを使用して、アクセス許可をプロンプトなしで自動で付与するか、プロンプトなしで自動で拒否するか、エンド ユーザーに決定させるかを設定できます。 次の中から選択します。
  - **デバイスの既定**
  - **プロンプト**
  - **自動許可**
  - **自動拒否**

  ( **[クライアント アプリ]**  >  **[アプリ構成ポリシー]** で) アプリ構成ポリシーを使用することで、個別のアプリにアクセス許可を付与することもできます。

- **[アカウントを追加および削除します]** : **[ブロック]** を選択すると、エンド ユーザーが仕事用プロファイルのアカウントを手動で追加または削除できなくなります。 たとえば、Android 仕事用プロファイルに Gmail アプリを展開する場合、エンド ユーザーがこの仕事用プロファイルのアカウントを追加または削除できないようにすることができます。 **[未構成]** では、仕事用プロファイルにアカウントを追加できるようになります。  

- **[Bluetooth 経由での連絡先の共有]** : Bluetooth を使用してペアリングされる、自動車などの別のデバイスから勤務先の連絡先にアクセスできるようにします。 既定では、この設定は構成されておらず、仕事用プロファイルの連絡先は表示されません。 **[有効にする]** を選択して、この共有を許可し、仕事用プロファイルの連絡先を表示します。 この設定は、Android OS v6.0 以降の Android 仕事用プロファイル デバイスに適用されます。 この設定を有効にすると、最初の接続時に特定の Bluetooth デバイスで勤務先の連絡先をキャッシュすることができます。 最初のペアリング/同期後にこのポリシーを無効にしても、Bluetooth デバイスから勤務先の連絡先が削除されないことがあります。

- **[画面の取り込み]** : **[ブロック]** を選択すると、仕事用プロファイルのデバイス上でスクリーンショットまたは画面の取り込みを実行できなくなります。 セキュリティで保護されたビデオ出力を持たないディスプレイ デバイスにもコンテンツが表示されないようになります。 **[未構成]** では、スクリーンショットを取得できるようになります。

- **[個人プロファイルに勤務先の連絡先の発信者番号を表示する]** : 有効にすると ( **[未構成]** )、勤務先の連絡先の発信者番号の詳細が個人プロファイルに表示されます。 **[ブロック]** に設定すると、勤務先の連絡先の発信者番号は個人プロファイルに表示されません。 Android OS v6.0 以降のバージョンに適用されます。

- **[個人プロファイルから仕事用の連絡先を検索する]** : **[ブロック]** を選択すると、個人プロファイルにあるアプリ内の勤務先の連絡先をユーザーが検索できなくなります。 **[必要なし]** では、個人プロファイルにある勤務先の連絡先を検索できるようになります。

- **[カメラ]** : **[ブロック]** を選択すると、仕事用プロファイルのデバイス上のカメラにアクセスできなくなります。 個人用のカメラは、設定の影響を受けません。 **[必要なし]** では、仕事用プロファイルのカメラにアクセスできるようになります。

- **仕事用プロファイルアプリからウィジェットを許可**する: **[有効]** に設定すると、エンドユーザーは、アプリによって公開されているウィジェットをホーム画面に配置できます。 **[未構成]** (既定) の場合、この機能が無効になります。

  たとえば、Outlook はユーザーの仕事用プロファイルにインストールされます。 **[有効]** に設定すると、ユーザーは、デバイスのホーム画面に議題ウィジェットを配置できます。

#### <a name="work-profile-password"></a>仕事用プロファイルのパスワード

- **[作業プロファイルのパスワードが必要です]** : 仕事用プロファイルが有効になっている Android 7.0 以降に適用されます。 **[必要]** を選択して、仕事用プロファイルのアプリにのみ適用されるパスコード ポリシーを入力します。 既定では、エンド ユーザーは別々に定義された 2 つの PIN を利用できます。あるいは、2 つの PIN のうちの強い方に PIN を統合することもできます。 **[未構成]** では、ユーザーがパスワードを入力せずに仕事用アプリを使用できるようになります。
- **[パスワードの最小文字数]** : ユーザーのパスワードに必要な文字の最小数 (**4**-**16**) を入力します。
- **[作業プロファイルがロックされるまでの非アクティブな最長時間 (分)]** : 仕事用プロファイルがロックされるまでの時間を選択します。 ユーザーが再度アクセスするには、資格情報を入力する必要があります。
- **[デバイスがワイプされるまでのサインイン失敗回数]** : 仕事用プロファイルがデバイスからワイプされるまでの、誤ったパスワードの入力可能回数を入力します。
- **[パスワードの有効期限 (日数)]** : エンド ユーザーのパスワードの変更が必要になるまでの日数 (**1**-**255**) を入力します。
- **[必要なパスワードの種類]** : デバイスに設定する必要があるパスワードの種類を選択します。 次の中から選択します。
  - **デバイスの既定**
  - **低レベルのバイオメトリック セキュリティ**
  - **必須**
  - **最小数の数字**
  - **[数値複素数]** : "1111" のような繰り返しの番号や、"1234" のような連続した番号は許可されません。
  - **最小数の英字**
  - **最小数の英数字**
  - **英数字と記号を使用する**
- **[以前のパスワードを再利用できないようにする]** : 以前のパスワードを再利用できるまでに使用する必要がある、新しいパスワードの数を入力します (**1**-**24**)。
- **[指紋によるロック解除]** : **[ブロック]** を選択すると、エンド ユーザーがデバイスの指紋スキャナーを使用してデバイスのロックを解除できなくなります。 **[未構成]** では、ユーザーが仕事用プロファイルの指紋を使ってデバイスのロックを解除できるようになります。
- **[Smart Lock などの信頼できるエージェント]** : **[ブロック]** を選択すると、互換性のあるデバイス上での、Smart Lock などの信頼できるエージェントによるロック画面設定の調整が禁止されます。 信頼エージェントと呼ばれることもあるこの機能では、デバイスが信頼できる場所にある場合、デバイスのロック画面のパスワードを無効化またはバイパスすることができます。 たとえば、デバイスが特定の Bluetooth デバイスに接続されているときや、NFC タグの近くにある場合に、仕事用プロファイルのパスワードをバイパスします。 この設定を使用して、ユーザーが SmartLock を構成することを禁止します。

### <a name="device-password"></a>デバイスのパスワード

これらのパスワード設定は、仕事用プロファイルを使用するデバイス上の個人プロファイルに適用されます。

- **[パスワードの最小文字数]** : ユーザーのパスワードに必要な文字の最小数 (**4**-**14**) を入力します。
- **[画面がロックされるまでの非アクティブな最長時間 (分)]** : 非アクティブなデバイスが自動的にロックされるまでの時間を選択します。
- **[デバイスがワイプされるまでのサインイン失敗回数]** : 間違ったパスワードをユーザーが何回入力すると、すべてのデータがそのデバイスからワイプされるかを入力します。
- **[パスワードの有効期限 (日数)]** : エンド ユーザーのパスワードの変更が必要になるまでの日数 (**1**-**255**) を入力します。
- **[必要なパスワードの種類]** : デバイスに設定する必要があるパスワードの種類を選択します。 次の中から選択します。
  - **デバイスの既定**
  - **低レベルのバイオメトリック セキュリティ**
  - **必須**
  - **最小数の数字**
  - **数値複素数**: "1111" のような繰り返しの番号や、"1234" のような連続した番号は許可されません。
  - **最小数の英字**
  - **最小数の英数字**
  - **英数字と記号を使用する**
- **[以前のパスワードを再利用できないようにする]** : 以前のパスワードを再利用できるまでに使用する必要がある、新しいパスワードの数を入力します (**1**-**24**)。
- **[指紋によるロック解除]** : **[ブロック]** を選択すると、エンド ユーザーがデバイスの指紋スキャナーを使用してデバイスのロックを解除できなくなります。 **[未構成]** では、ユーザーが指紋を使用してデバイスをロック解除できるようになります。
- **[Smart Lock などの信頼できるエージェント]** : **[ブロック]** を選択すると、互換性のあるデバイス上での、Smart Lock などの信頼できるエージェントによるロック画面設定の調整が禁止されます。 信頼エージェントと呼ばれることもあるこの機能では、デバイスが信頼できる場所にある場合、デバイスのロック画面のパスワードを無効化またはバイパスすることができます。 たとえば、デバイスが特定の Bluetooth デバイスに接続されているときや、NFC タグの近くにある場合に、仕事用プロファイルのパスワードをバイパスします。 この設定を使用して、ユーザーが SmartLock を構成することを禁止します。

### <a name="system-security"></a>システム セキュリティ

- **[アプリの脅威のスキャン]** : **[必要]** では、仕事用および個人プロファイルに対して **[アプリの確認]** 設定が強制的に有効になります。

   > [!Note]
   > この設定は、Android O 以降のデバイスでのみ機能します。

- **個人プロファイルの不明なソースからのアプリのインストールを禁止する**: 仕様では、Android Enterprise work profile デバイスは、Play ストア以外のソースからアプリをインストールすることはできません。 本質的に、仕事用プロファイルデバイスはデュアルプロファイルを想定しています。

  - MDM を使用して管理されている仕事用プロファイル。
  - MDM 管理から分離された個人プロファイル。

  この設定により、管理者は不明なソースからのアプリのインストールをより細かく制御できます。 **未構成**(既定) では、個人プロファイルの不明なソースからのアプリのインストールが許可されます。 **ブロック**は、個人プロファイル内の Play ストア以外のソースからのアプリのインストールを防止します。

### <a name="connectivity"></a>接続

- **常時接続 VPN**: VPN に自動的に接続および再接続するように VPN クライアントを設定するには、 **[有効化]** を選択します。 常時接続 VPN は接続されたままの状態になるか、ユーザーが自分のデバイスをロックした場合、デバイスが再起動した場合、またはワイヤレス ネットワークに変更があった場合に、すぐに接続されます。 

  すべての VPN クライアントの常時接続 VPN を無効にするには、 **[未構成]** を選択します。

  > [!IMPORTANT]
  > 1 つのデバイスには Always On VPN ポリシーを 1 つだけ展開してください。 1 つのデバイスに複数の常時接続 VPN ポリシーを展開することはサポートされていません。

- **VPN クライアント**: Always On をサポートする VPN クライアントを選択します。 次のようなオプションがあります。
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - カスタム
    - **パッケージ ID**: Google Play ストアでのアプリのパッケージ ID を入力します。 たとえば、Play ストアでのアプリの URL が `https://play.google.com/store/details?id=com.contosovpn.android.prod` の場合、パッケージ ID は `com.contosovpn.android.prod` になります。

  > [!IMPORTANT]
  > - 選択した VPN クライアントは、デバイスにインストールされている必要があり、仕事用プロファイルでアプリごとの VPN をサポートしている必要があります。 そうでない場合、エラーが発生します。 
  > - **Managed Google Play ストア**で VPN クライアント アプリを承認し、アプリを Intune に同期して、アプリをデバイスに展開する必要があります。 これを行うと、アプリがユーザーの仕事用プロファイルにインストールされます。
  > - Android 3.0.4 用の F5 Access と共にアプリごとの VPN を使用する場合、既知の問題がある可能性があります。 詳細については、[Android 3.0.4 用の F5 Access に向けた F5 のリリース ノート](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android)をご覧ください。

- **ロックダウン モード**: すべてのネットワーク トラフィックで VPN トンネルの使用を強制するには、 **[有効化]** を選択します。 VPN への接続が確立されていない場合、デバイスはネットワークにアクセスできません。

  VPN トンネルまたはモバイル ネットワークを経由したトラフィック フローを許可するには、 **[未構成]** を選択します。

## <a name="next-steps"></a>次の手順

[プロファイルを割り当て](device-profile-assign.md)、[その状態を監視](device-profile-monitor.md)します。

[Android](device-restrictions-android.md#kiosk) と [Windows 10](kiosk-settings.md) デバイスに対して専用デバイスのキオスク プロファイルを作成することもできます。

## <a name="see-also"></a>関連項目

[Microsoft Intune での Android エンタープライズ デバイスの構成とトラブルシューティング](https://support.microsoft.com/help/4476974)