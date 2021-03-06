---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-01"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}

# 資格情報の概要
{: #credentials_overview}

デプロイメント環境にサービス資格情報を手動で追加する方法について説明します。
{: shortdesc}

<!-- After PUP: Maybe provide links to the credentials section of the programming guides, such as https://cloud.ibm.com/docs/swift/cloudnative/configuration.html#configuration-->

一般的に、アプリケーション・ロジックでは、データベース API キーやパスワードなどの機密性の高いサービス資格情報は、アプリケーションが実行される環境から取得することが望まれます。 この方法では、資格情報をソース・コード・リポジトリー内に保持しません。 継続的統合環境、実動前環境、および実稼働環境のデータベースは、互いに隔離されます。

スターター・キット・テンプレートを使用してアプリを作成すると、環境が自動的に準備されます。 デプロイメント・ターゲットが以下のいずれであろうと、関係ありません。
  * [Kubernetes](/docs/apps/creds_kube.html#add-credentials-kube)
  * [Cloud Foundry パブリックまたは Cloud Foundry エンタープライズ環境](/docs/apps/creds_cf.html#add-credentials-cf)
  * [仮想サーバー・インスタンス (ローカル Docker も含む)](/docs/apps/creds_vsi.html#add-credentials-vsi)
  
環境を構成する方法についての手順が用意されています。 スターター・キットは、依存ライブラリーを使用するコードを生成して、任意のデプロイメント・ターゲットで実行できるようにコードを移植可能にします。 最後に、アプリケーションが実行されているデプロイメント・ターゲットを検出するためにブランチ・ロジックは使用されません。

その後は、管理者または DevOps エンジニアが環境を準備する責任を負い、アプリケーションが必要な値を使用できるように、適切なアクセス制御および構成を設定します。

「クラウドへのデプロイ」は、以下の主要なタスクを実行する一回限りのステップです。
 * ターゲット・デプロイメント環境にサービス、リソース、および資格情報を準備する。
 * 環境内の資格情報を正しく参照するコードを使用することで、アプリをビルドしてその環境にデプロイするための DevOps ツールチェーンを作成する。

ただし、以下のシナリオでは、ユーザーがターゲット・デプロイメント環境を準備する必要があります。
 * 独自のコードを持ち込む (Bring Your Own Code)。
 * ブランクのスターター・キット・テンプレートから開始する。
 * デプロイされた_後_ のスターター・キット・ベースのアプリにサービスを追加する。




