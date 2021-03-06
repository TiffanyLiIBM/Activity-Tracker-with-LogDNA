---

copyright:
  years: 2019
lastupdated: "2019-06-06"

keywords: IBM Cloud, LogDNA, Activity Tracker, getting started

subcollection: logdnaat

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}


# 入門チュートリアル
{: #getting-started}

{{site.data.keyword.at_full}} サービスを使用して、{{site.data.keyword.cloud_notm}} アカウントのアクティビティーをモニターします。このサービスを使用して、異常なアクティビティーや重大なアクションがないかを調査し、規制当局の監査条件に適合させることができます。 さらに、アクションが発生した際にそれに関するアラートを通知させるようにできます。収集されるイベントは、Cloud Auditing Data Federation (CADF) 標準に準拠しています。
{:shortdesc}

![{{site.data.keyword.at_full_notm}} サービス](images/atov.png "{{site.data.keyword.at_full_notm}} サービス")


{{site.data.keyword.at_full_notm}} は、 {{site.data.keyword.cloud_notm}} で実行されるリソースに対する API 呼び出しの監査レコードを収集し、保管します。 これらのイベントは  {{site.data.keyword.cloud_notm}} にアーカイブして、長期的に保管できます。
{: note}



## {{site.data.keyword.at_full}} について
{: #gs_ov}

アプリケーションの実行場所がオンプレミス、ハイブリッド・クラウド、またはパブリック・クラウドのいずれであるかに関係なく、社内のポリシーおよび業界の規定に準拠することは、すべての組織の戦略にとって重要な要件です。 {{site.data.keyword.at_full_notm}} サービスは {{site.data.keyword.cloud_notm}} 上のサービスへの API 呼び出しをモニターするためのフレームワークおよび機能を提供し、企業のポリシーおよび市場の業界固有の規定への準拠の証拠を生成します。

クラウド環境 ({{site.data.keyword.cloud_notm}} など) で作業をする場合、社内のポリシーと業界や国ベースの準拠要件に従って、ワークロードやデータの監査とモニターに関するクラウド戦略を立てる必要があります。 {{site.data.keyword.at_full_notm}} サービスを通じて登録された情報を使用することで、セキュリティー・インシデントを特定し、無許可アクセスを検出して、規制上および社内の監査要件に準拠することができます。

* {{site.data.keyword.at_full_notm}} は、クラウド内の IT リソースに対する高水準のセキュリティー・ガバナンスをサポートします。
* {{site.data.keyword.at_full_notm}} は、管理者が 1 つの場所で API アクティビティーの取り込み、保管、表示、検索、およびモニターを行えるようにするソリューションを提供します。 また、サポートされているいずれかの通知チャネルを使用してアラートを通知する機能も提供しています。
* {{site.data.keyword.at_full_notm}} は、イベントをダウンロードする機能を提供します。エクスポートしたイベントは監査証跡レポートを生成するために使用できます。 組織が社内規定および外部の業界や国の規制に準拠するために、これらのレポートが必要になることがあります。

![{{site.data.keyword.at_full_notm}} サービスによって提供される中核機能](images/features.png "{{site.data.keyword.at_full_notm}} サービスによって提供される中核機能")

例えば、{{site.data.keyword.at_full_notm}} イベントを使用して、以下の情報を識別できます。
* クラウド・サービスに対して API 呼び出しを行ったユーザー
* API 呼び出しが行われたタイム・スタンプ
* API 呼び出しの状況
* アクションの重大度


{{site.data.keyword.at_full_notm}} サービスでの処理を行うときには、セキュリティーに関する以下の情報を考慮してください。

* {{site.data.keyword.at_full_notm}} イベントを生成する IBM サービスは、{{site.data.keyword.IBM_notm}} クラウドのセキュリティー・ポリシーに従います。 詳しくは、[Trust the security and privacy of IBM Cloud ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/cloud/security){: new_window} を参照してください。
* {{site.data.keyword.at_full_notm}} サービスは、クラウド・サービスの状態を変更するユーザー開始アクションを取り込みます。 この情報からデータベースまたはアプリケーションに直接アクセスすることはできません。
* 許可されたユーザーのみが {{site.data.keyword.at_full_notm}} イベント・ログの表示およびモニターを行うことができます。 各ユーザーは、{{site.data.keyword.cloud_notm}} での固有の ID によって識別されます。
* プロビジョンできるサービスのインスタンスは {{site.data.keyword.cloud_notm}} のロケーション (地域) につき 1 つのみです。


## 達成目標
{: #gs_objectives}

このチュートリアルを完了すると、{{site.data.keyword.cloud_notm}} でサービスをプロビジョンする方法を学習できます。 各イベントでどの一般的なデータが使用できるか、お使いのクラウド環境の監視のにどのように役立てることができるかを学びます。 Web UI でのナビゲートについて学びます。 


## 前提条件
{: #gs_prereq}

* {{site.data.keyword.cloud_notm}} アカウントのメンバーまたは所有者であるユーザー ID が必要です。 {{site.data.keyword.cloud_notm}} ユーザー ID を取得するには、[登録 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/login){:new_window} に移動してください。

* コマンド・ラインを使用して作業する方法を選ぶ場合は、{{site.data.keyword.cloud_notm}} CLI をインストールする必要があります。 詳しくは、[『{{site.data.keyword.cloud_notm}}CLI のインストール』](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)を参照してください。

* サービスへのアクセスを管理する手順を実行するには、ユーザー ID に、{{site.data.keyword.at_full_notm}} サービスを管理するための**管理者プラットフォーム権限**が必要です。アカウント管理者にお問い合わせください。アカウント所有者は、ユーザー・アクセスの管理とアカウント・リソースの管理を行う目的で、別のユーザーにアカウントへのアクセス権限を付与できます。[詳細はこちら](/docs/iam?topic=iam-userroles)。



## ステップ 1. {{site.data.keyword.at_full_notm}} のインスタンスをプロビジョンする
{: #gs_step1}

インスタンスをプロビジョンするには、以下のステップを実行します。

1. [{{site.data.keyword.cloud_notm}} アカウントにログイン ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/login){:new_window} します。

	ユーザー ID とパスワードを使用してログインすると、{{site.data.keyword.cloud_notm}} UI が開きます。

2. メニュー・アイコン ![メニュー・アイコン](../../icons/icon_hamburger.svg) に移動します。 その後、**「プログラム識別情報」**を選択して、*「プログラム識別情報」*ダッシュボードにアクセスします。

3. **「Activity Tracker」**を選択してから、**「インスタンスの作成」**をクリックします。 

4. サービス・インスタンスの名前を入力します。

5. ロケーションとして**「フランクフルト」**を選択します。 

    サービスが使用可能な地域について詳しくは、[地域](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-regions)を参照してください。

6. リソース・グループを選択します。 

    デフォルトでは、**default** リソース・グループが設定されています。

    **注:** リソース・グループを選択できない場合、インスタンスをプロビジョンするリソース・グループでの編集許可があることを確認してください。

7. `「ライト」`サービス・プランを選択します。 

    デフォルトでは、ライト・プランが設定されます。

8. **「作成」**をクリックします。

インスタンスがプロビジョンされると、*「Activity Tracker」*ダッシュボードが開きます。 


## ステップ 2. サービスへのアクセスを管理する
{: #gs_step2}

**ご使用のアカウント内の {{site.data.keyword.at_full_notm}} サービスにアクセスするすべてのユーザーには、IAM ユーザー役割が定義されたアクセス・ポリシーを割り当てる必要があります。** そのポリシーによって、選択したサービスまたはインスタンスのコンテキスト内でユーザーが実行できるアクションが決まります。 許可されるアクションは、サービス上で実行できる操作としてカスタマイズされて定義されます。 その後、操作は IAM ユーザー役割にマップされます。 [詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam)。

このチュートリアルでは、リソース・グループのコンテキスト内で、{{site.data.keyword.at_full_notm}} サービスを使用して作業するための管理権限をユーザーに付与する方法を学習します。


### 1. アクセス・グループを作成する
{: #gs_step2_1}

アクセス・グループを作成するには、以下のステップを実行します。
1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. **「作成」**をクリックします。
3. グループの名前と説明 (オプション) を入力して**「作成」**をクリックします。

### 2. イベントを管理する権限を追加する
{: #gs_step2_2}

グループをセットアップした後で、共通するアクセス・ポリシーをそのグループに割り当てる必要があります。アクセス・グループに設定するポリシーは、そのグループ内のすべてのエンティティー、ユーザー、およびサービス ID に適用されます。

ポリシーを定義するときには、プラットフォーム役割とサービス役割を選択する必要があります。
* プラットフォーム管理の役割は、インスタンスの作成と削除、別名、バインディング、および資格情報の管理、およびアクセスの管理を行う能力を含めて、さまざまなアクションをカバーします。プラットフォームの役割は、管理者、エディター、オペレーター、ビューアーです。プラットフォーム管理の役割は、アカウント管理サービスにも適用され、ユーザーが、アカウント管理サービスに関して割り当てられた役割に応じて、ユーザーの招待、サービス ID の管理、アクセス・ポリシーの管理、カタログ・エントリーの管理、請求および使用量の追跡を行うことを可能にします。
* サービス・アクセスの役割は、ユーザーまたはサービスの、サービス・インスタンスに関するアクションを実行する能力を定義します。サービス・アクセスの役割は、管理者、ライター、およびリーダーです。

{{site.data.keyword.at_full_notm}} サービスを管理するには、ユーザーに以下の役割が必要です。
* プラットフォーム役割: **管理者**。 
* サービス役割: **管理者**。 


UI を使ってポリシーを割り当てるには、以下のステップを実行します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックします。
2. **「アクセス・グループ」**を選択します。
3. アクセス権限を割り当てる先のグループの名前を選択します。 
4. **「アクセス・ポリシー」**をクリックします。
5. **「アクセス権限の割り当て (Assign access)」**をクリックします。
6. **「リソース・グループ内のアクセス権限の割り当て」**を選択します。
7. リソース・グループを選択します。
8. 選択したリソース・グループに対する役割がまだユーザーに付与されていない場合は、**「リソース・グループへのアクセス権限の割り当て」**フィールドで役割を選択します。 

    選択する役割に応じて、ユーザーはダッシュボードでのリソース・グループの表示、リソース・グループ名の編集、またはグループへのユーザー・アクセスの管理を行うことができます。 
    
    リソース・グループ内の {{site.data.keyword.at_full_notm}} サービスへのアクセス権限のみをユーザーに付与する場合は、**「アクセス権限なし」**を選択します。

9. **「IBM Cloud Activity Tracker with LogDNA」**を選択します。
10. **「管理者」**プラットフォーム役割を選択します。
11. **「管理者」**サービス役割を選択します。
12. **「割り当て」**をクリックします。


### 3. ユーザーをグループに追加する
{: #gs_step2_3}

アクセス・グループにユーザーを追加するには、以下のステップを実行します。
1. **「ユーザー」**タブで**「ユーザーの追加」**をクリックします。
2. 追加するユーザーをリストから選択して、**「グループに追加」**をクリックします。


## ステップ 3. {{site.data.keyword.at_full_notm}} イベントを生成する
{: #gs_step3}

{{site.data.keyword.cloudcerts_short}} サービスのインスタンスがプロビジョンされたときにイベントを生成するには、以下のステップを実行します。


1. [{{site.data.keyword.cloud_notm}} カタログ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/catalog){:new_window} から、**「セキュリティーおよび ID」**のカテゴリーを選択します。

2. {{site.data.keyword.cloudcerts_short}} サービスを選択します。

3. サービス・インスタンスの名前を入力します。

4. インスタンスをプロビジョンすることを計画している地域を選択します。

5. リソース・グループを選択します。 

    デフォルトでは、**Default** リソース・グループが設定されます。

    **注:** リソース・グループを選択できない場合、インスタンスをプロビジョンするリソース・グループでの編集許可があることを確認してください。

6. `「無料」`サービス・プランを選択します。 

7. **「作成」**をクリックします。

{{site.data.keyword.cloudcerts_short}} サービスのインスタンスが作成されます。

## ステップ 4. Web UI を起動する 
{: #gs_step4}

Web UI を起動するには、以下の手順を実行します。

1. [{{site.data.keyword.cloud_notm}} アカウントにログイン ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/login){:new_window} します。

	ユーザー ID とパスワードを使用してログインすると、{{site.data.keyword.cloud_notm}} ダッシュボードが開きます。

2. ナビゲーション・メニューで、**「プログラム識別情報」**を選択します。 

3. **「Activity Tracker」**を選択します。 

    {{site.data.keyword.cloud_notm}} で使用可能なインスタンスのリストが表示されます。

4. **フランクフルト**にあるインスタンスを選択します。次に、**「LogDNA の表示 (View LogDNA)」**をクリックします。

    グローバル・イベント (サービスのプロビジョニングなど) は、フランクフルトにあるグローバル・ドメイン・インスタンスを介して使用できます。

Web UI が開きます。 


## ステップ 5. イベントを表示する
{: #gs_step5}


{{site.data.keyword.at_full_notm}} サービスは、{{site.data.keyword.cloud_notm}} 内の選択されたクラウド・サービスに対して行われる API 呼び出しおよびその他のアクションに関連したアクティビティー・データを取り込みます。 

* イベントは自動的に収集されます。 
* {{site.data.keyword.at_full_notm}} で収集されるイベントは、**Cloud Auditing Data Federation (CADF) 標準**に準拠しています。 CADF 標準は、クラウド環境にあるアプリケーションのセキュリティーの認証、管理、および監査に必要な情報が含まれた、フルイベント・モデルを定義しています。
* {{site.data.keyword.at_full_notm}} は、ロケーション別にイベントを保管およびグループ化します。 
* {{site.data.keyword.cloud_notm}} のグローバル・アカウントのアクションに関するレポートを作成するイベントが**フランクフルト (EU-DE)** 地域で収集され、保管されます。
* {{site.data.keyword.at_full_notm}} インスタンス用に選択するサービス・プランによって、Web UI でイベントを検索可能な日数が設定されます。 

Web UI が開くと、**「すべて (Everything)」**ビューが表示されます。このビューを介してイベントを表示できます。

カスタム・ビューを定義して、タイム・スタンプ、検索照会、またはその両方を適用することにより、一連のイベントを表示することもできます。[詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。


## ステップ 6. イベントの構造について学習する
{: #gs_step6}

イベントは **Cloud Auditing Data Federation (CADF) 標準**に準拠しています。 CADF 標準は、クラウド環境にあるアプリケーションのセキュリティーの認証、管理、および監査に必要な情報が含まれた、フルイベント・モデルを定義しています。

CADF イベント・モデルには、以下のコンポーネントが含まれています。

| コンポーネント | 説明 |
|------------|----------------------------|
| `アクション`   | アクションは、イニシエーターが実行する、実行を試みる、あるいは完了を待っている、操作またはアクティビティーです。 |
| `イニシエーター`| イニシエーターは、API 呼び出しを行って CADF イベントを生成するリソースです。 起動されるイベントは、API 呼び出しで要求されるアクションによって異なります。 |
| `オブザーバー` | オブザーバーは、CADF イベントで利用可能な情報から CADF レコードを作成して保管するリソースです。 |
| `結果`  | 結果は、ターゲットに対するアクションの状況です。 |
| `ターゲット`   | ターゲットは、アクションが実行される、実行を試みられる、あるいは完了の処理待ち中の、対象のリソースです。 |
{: caption="表 2. CADF イベント・モデル内のコンポーネント" caption-side="top"} 

[詳細はこちら](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-event#event)。



## 次のステップ
{: #gs_next_steps}

[カスタム・ビューを定義します](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views)。 

{{site.data.keyword.at_full_notm}} サービス・プランを、[照会を適用することによるイベントの検索](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2)および[アラートの構成](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts)を行える有料プランにアップグレードします。 

{{site.data.keyword.at_full_notm}} サービス・プランについて詳しくは、[サービス・プラン](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan)を参照してください。

