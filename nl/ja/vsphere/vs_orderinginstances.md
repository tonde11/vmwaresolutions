---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-11"

---

{:tip: .tip}

# 新規 vSphere クラスターの注文

高度にカスタマイズ可能な VMware 仮想化プラットフォームをデプロイするには、VMware vSphere cluster on {{site.data.keyword.cloud}} を注文します。 次の手順を使用して、新規の VMware vSphere クラスターを定義してください。

この手順では、新規クラスターを作成するための VMware コンポーネントの選択、{{site.data.keyword.cloud_notm}} ベア・メタル・サーバーの設定、ストレージ設定、およびネットワーキングの選択について説明します。 注文を実行すると、そのクラスター構成が取り込まれるので、必要なときに構成に戻ってクラスターをスケールアウトできます。 注文が完了したら、要件に応じて VMware クラスターを手動で構成できます。

## 要件

以下の作業を完了していることを確認してください。
*  **「設定」**ページで {{site.data.keyword.cloud_notm}} インフラストラクチャーの資格情報を構成する。 詳しくは、[ユーザー・アカウントと設定の管理](../vmonic/useraccount.html)を参照してください。
*  [vSphere クラスターの要件と計画](vs_planning.html)に記載されている要件と考慮事項を確認する。

## システム設定

新しい vSphere クラスターを注文する際には、以下のシステム設定を指定する必要があります。

### クラスター名

クラスター名は、アカウント内で固有でなければなりません。

## ライセンス交付の設定

クラスターと一緒に注文する VMware コンポーネントを選択し、それらのコンポーネントのライセンス・オプションを指定します。

### (IBM ビジネス・パートナーのみ) コンポーネント・バンドル

IBM ビジネス・パートナーは、新規 vSphere クラスターを注文するときにコンポーネント・ライセンス・バンドルを選択できます。 使用可能なバンドルは次のとおりです。

表 1. IBM ビジネス・パートナー向けの vSphere クラスター用のコンポーネント・バンドル

| バンドル | コンポーネント                   |
|:------------------------- |:----------------------- |
| Standard with Management | vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight、vRealize Operations Enterprise |
| Advanced                 | vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight、vCloud Director、NSX Base |
| Advanced with Networking | vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight、NSX Advanced |
| Advanced with Networking and Management | vSphere Enterprise Plus、vCenter Server Standard、vRealize Log Insight、vRealize Operations Enterprise、vCloud Director、NSX Enterprise |

また、次の VMware コンポーネントを注文に含めることもできます。
* VMware vSAN
* VMware Site Recovery Manager
* VMware vRealize Automation Enterprise

**注:** IBM ビジネス・パートナーの場合、ライセンス持ち込み (BYOL) オプションは利用できません。

### (非ビジネス・パートナーのみ) 個別のコンポーネント

非ビジネス・パートナーは、vSphere クラスターに以下の VMware コンポーネントを柔軟に選択できます。
* VMware vSphere Enterprise Plus
* VMware vCenter Server
* VMware NSX
* VMware vSAN
* VMware Site Recovery Manager
* VMware vRealize Automation Enterprise
* VMware vRealize Operation Enterprise
* VMware vRealize Log Insight

**注:** VMware vSphere Enterprise Plus 6.0 を注文する場合、VMware vSAN コンポーネントは使用できません。 VMware vSphere Enterprise Plus 6.0 にお客様自身のライセンスを使用する場合は、{{site.data.keyword.cloud_notm}} インフラストラクチャー・チケットが自動的にオープンされます。 このチケットは、注文した{{site.data.keyword.baremetal_short}}の vSphere ライセンスを、提供したライセンスに置き換えるように要求します。

### ライセンス・オプション

選択した VMware コンポーネントにライセンスを適用するには、次の方法があります。
* **購入にライセンスを含める**: この場合、自動的に VMware コンポーネントの新規ライセンスを購入します。 結合された VMware ライセンスが、注文のクラスター・サイズに一致するように生成されます。
* **自分でライセンスを提供する**: この場合、VMware コンポーネントにお客様自身のライセンスを使用します。

vSphere Enterprise Plus と vCenter Server を除き、ライセンスを購入することを選択して複数の ESXi サーバーを注文した場合は、複数のライセンス・キーを結合するための {{site.data.keyword.cloud_notm}} チケットが自動的にオープンされます。 このチケットに対応し、DevOps チームで生成したライセンス・キーだけを使用するようにする作業は、お客様が行う必要があります。

**重要**: 個々のライセンス・キーを、結合されたライセンス・キーと一緒に使用しても、必要なライセンスの支払要件は満たされません。

## ベア・メタル・サーバーの設定

### データ・センターの場所

クラスターをホストする {{site.data.keyword.CloudDataCent_notm}}を選択します。

**注:** vSAN コンポーネントを選択した場合は、SSD の使用可否によってロケーション・リストがフィルタリングされます。

### CPU モデルと RAM

ベア・メタル・サーバーの CPU モデルと RAM を指定します。

表 2. カスタマイズ型{{site.data.keyword.baremetal_short}}のオプション

| CPU モデル・オプション        | RAM オプション       |
|:------------- |:------------- |
| デュアル Intel Xeon E5-2620 v4 / 合計 16 コア、2.1 GHz | 64 GB、128 GB、256 GB、384 GB、512 GB、768 GB、1.5 TB |
| デュアル Intel Xeon E5-2650 v4 / 合計 24 コア、2.2 GHz | 64 GB、128 GB、256 GB、384 GB、512 GB、768 GB、1.5 TB |
| デュアル Intel Xeon E5-2690 v4 / 合計 28 コア、2.6 GHz | 64 GB、128 GB、256 GB、384 GB、512 GB、768 GB、1.5 TB |
| Dual Intel Xeon Silver 4110 Processor / 合計 16 コア、2.1 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 5120 Processor / 合計 28 コア、2.2 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |
| Dual Intel Xeon Gold 6140 Processor / 合計 36 コア、2.3 GHz | 64 GB、96 GB、128 GB、192 GB、384 GB、768 GB、1.5 TB |

使用できるオプションは、VMware vSAN コンポーネントを選択したかどうかによって異なります。

### ベア・メタル・サーバーの数

vSphere クラスターに追加する ESXi サーバーの数。 すべての ESXi サーバーが同じ構成です。
* VMware NSX コンポーネントを選択した場合は、最少 3 台のサーバーが必要です。
* VMware vSAN コンポーネントを選択した場合は、最少 4 台のサーバーが必要です。

## ストレージ設定

vSAN なしの注文の場合、ESXi サーバー用に 12 ディスクのシャーシと 2 基のディスク (ESXi オペレーティング・システム (OS) 用) が注文されます。

vSAN ありの注文の場合、ESXi サーバー用に 12 ディスクのシャーシと 4 基のディスク (ESXi OS 用の 2 基とキャッシュ用に予約された 2 基) が注文されます。 これらの設定はデフォルトで構成され、変更はできません。 **「vSAN 容量ディスクのディスク・タイプとサイズ」**および**「vSAN 容量ディスクの数」**を選択して、追加の容量ディスクを注文できます。

クラスターに VMware vSAN コンポーネントを選択した場合は、以下の設定を指定します。

### vSAN 容量ディスクのディスク・タイプとサイズ

このオプションは、VMware vSAN コンポーネントを選択した場合にのみ使用可能です。

以下のディスク・タイプを選択できます。
* 960 GB SSD SED
* 1.9 TB SSD SED
* 3.8 TB SSD SED (3.8 TB SSD SED ドライブはデータ・センターで一般提供が開始されたらサポートされます)

### vSAN 容量ディスクの数

このオプションは、VMware vSAN コンポーネントを選択した場合にのみ使用可能です。 ディスク数のオプションには、2、4、6、および 8 があります。

## ネットワーク・インターフェースの設定

新しい vSphere クラスターを注文する際には、以下のネットワーク・インターフェース設定を指定する必要があります。

### ホスト名接頭部

ホスト名は、すべてのベア・メタル・サーバーの注文で使用されます。 vCenter Server および NSX などのすべての管理仮想マシンで、このホスト名を使用することをお勧めします。

ホスト名接頭部は、次の要件を満たす必要があります。
* この名前の先頭と末尾は英数字である必要があります。
* 英数字とダッシュ (-) の文字だけを使用できます。
* 最大長は 10 文字です。

### サブドメイン・ラベル

サブドメイン・ラベルは、次の要件を満たす必要があります。
*  英数字とダッシュ (-) の文字だけを使用できます。
*  サブドメイン・ラベルの先頭と末尾は英数字である必要があります。
*  サブドメイン・ラベルの最大長は 10 文字です。
*  サブドメイン・ラベルは、アカウント内で固有でなければなりません。

### ドメイン・ネーム

ドメイン・ネームは、すべての{{site.data.keyword.baremetal_short}}で使用されます。次の要件を満たす必要があります。
* ピリオド (.) で区切られた 2 つ以上の文字列で構成された名前である必要があります。
* 英数字とダッシュ (-) の文字だけを使用できます。
* 各文字列は英字で始まり英数字で終わる必要があり、最後の文字列には英字しか含められません。
* 最後の文字列の長さは、2 文字から 24 文字までの範囲でなければなりません。
* 他の文字列の長さは、1 文字から 63 文字までの範囲でなければなりません。
* ドメイン・ネームの最大長は 189 文字です。

### VLAN

ネットワーク設定は、**「新規 VLAN を注文」**と**「既存の VLAN を選択」**のどちらを選択するかによって異なります。

クラスターの注文には、パブリック VLAN 1 つとプライベート VLAN 2 つが必要です。 2 つのプライベート VLAN は各ベア・メタル・サーバーにトランキングされます。

#### 新規 VLAN を注文
新規パブリック VLAN 1 つと新規プライベート VLAN 2 つを注文することを選択します。

#### 既存の VLAN を選択  
選択した {{site.data.keyword.CloudDataCent_notm}}によっては、既存のパブリック VLAN とプライベート VLAN を使用できることがあります。

  既存のパブリック VLAN とプライベート VLAN を再使用することを選択した場合は、それらの VLAN とサブネットを指定します。
  * **パブリック VLAN** は、パブリック・ネットワーク・アクセスに使用されます。
  * **プライベート VLAN** は、{{site.data.keyword.cloud_notm}} 内部のデータ・センターとサービスの間の接続に使用されます。
  * **セカンダリー・プライベート VLAN** は、vSAN などの VMware 機能に使用されます。
  * **プライマリー・サブネット**は、パブリック・ネットワーク・アクセス用に物理ホストに割り当てられます。
  * **プライマリー・プライベート・サブネット**は、管理トラフィック用に物理ホストに割り当てられます。

**重要:**
* 選択した VLAN のファイアウォール構成が管理用データ・トラフィックをブロックしていないことを確認してください。
* 選択したすべての VLAN が同じポッドに含まれていることを確認してください。 複数のポッドの VLAN に ESXi サーバーをプロビジョンすることはできません。

#### FortiGate 物理アプライアンス 300 シリーズ HA ペア

また、クラウド環境を保護するために FortiGate 物理アプライアンス 300 シリーズ HA ペアを含めるかどうかも選択できます。 詳しくは、[FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} の概要](../services/fsa_considerations.html)を参照してください。

## 注文のサマリー

構成に基づいて、見積もりコストがすぐに生成され、右側の**「注文の要約」**ペインに表示されます。 **「料金詳細」**をクリックすると、見積もりの詳細を示す PDF 文書を生成できます。

## 手順

1. {{site.data.keyword.cloud_notm}} のカタログで、左側のナビゲーション・ペインの**「VMware」**をクリックしてから、**「仮想データ・センター」**セクションの**「VMware vSphere」**をクリックします。
2. **「VMware vSphere on IBM Cloud」**ページで、**「作成」**をクリックします。  
   **「新規作成」**タブが表示され、**「クラスター構成」**リストに**「新規クラスター」**が表示されていることを確認します。
3. クラスター名を入力します。
4. VMware コンポーネントを選択します。
  * IBM ビジネス・パートナーは、ライセンス・バンドルと追加の VMware コンポーネントを選択してください。
  * 非ビジネス・パートナーは、コンポーネントとエディション (ある場合) を選択して、ライセンス・オプションを指定してください。
  VMware vSphere Enterprise Plus でライセンス持ち込み (BYOL) を選択すると、注文した{{site.data.keyword.baremetal_short}}のデフォルトの vSphere ライセンスを、自分で提供したライセンスに置き換えるよう要求する {{site.data.keyword.cloud_notm}} チケットが自動的に開きます。   

    **重要:** このチケットを追跡し、新しく注文した ESXi サーバー上で vSphere ライセンスを置き換える作業は、お客様が行う必要があります。 このようにして、最初に提供された {{site.data.keyword.cloud_notm}} インフラストラクチャーの vSphere ライセンス料の取り消しが {{site.data.keyword.cloud_notm}} インフラストラクチャーによって許可されます。 ESXi vSphere ライセンスを置き換えるには、[Configure License Settings for an ESXi Host](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.vcenterhost.doc/GUID-1B128360-0060-40F2-A6F0-43CD2534B034.html){:new_window}を参照してください。

5. ベア・メタル・サーバーの設定を次の手順で実行します。
   1. クラスターをホストする {{site.data.keyword.CloudDataCent_notm}}を選択します。
   2. CPU モデルと RAM サイズを選択します。
   3. ベア・メタル・サーバーの数を指定します。
6. **「VMware vSAN」**コンポーネントを選択した場合は、**「vSAN 容量ディスクのディスク・タイプとサイズ」**と**「vSAN 容量ディスクの数」**を選択して、vSAN ストレージ設定を行います。
7. ネットワーク・インターフェースの設定を行います。
   1. ホスト名接頭部、サブドメイン・ラベル、およびドメイン・ネームを入力します。
   2. 使用するネットワーク・インターフェースを選択します。
    * 新規のパブリック VLAN とプライベート VLAN を注文する場合は、**「新規 VLAN を注文」**をクリックします。
    * 既存のパブリック VLAN とプライベート VLAN を使用できる場合に再利用するには、**「既存の VLAN を選択」**をクリックし、該当する VLAN とオプションでサブネットを指定します。
    3. クラウド環境を保護するために FortiGate 物理アプライアンス 300 シリーズ HA ペアを適用するかどうかを指定します。  
8. **「注文のサマリー」**ペインで、クラスター構成と見積もりコストを確認します。
   * 注文を実行せずに構成をテンプレートとして保存するには、**「構成の保存」**をクリックします。
   * 注文を実行するには、課金されるアカウントが正しいことを確認し、使用条件を確認して承諾してから、**「プロビジョン」**をクリックします。

   **注**: {{site.data.keyword.baremetal_short}}だけがインストールされます。 クラスターのデプロイメントの後に、VMware vCenter、VMware NSX、VMware vSAN などの各種コンポーネントをインストールして構成する作業は、お客様が行う必要があります。

### 結果

クラスター構成をテンプレートとして保存した場合は、その構成が正常に保存されたことを示すコンソール通知を受け取ります。そして、**「クラスター構成」**リストにそのテンプレートが表示されます。

注文を実行した場合は、クラスターのデプロイメントが自動的に開始され、注文が処理中であることを示す E メール確認を受け取ります。 クラスターが使用可能になると、E メールで通知されます。

**注:** vSphere クラスターは、vCenter Server インスタンスや Cloud Foundation インスタンスとは異なり、**「デプロイ済みインスタンス」**ページに表示されません。

### 関連リンク

* [既存の構成を基にした vSphere クラスターの注文](vs_orderingbasedonexistingconfig.html)
* [既存クラスターの拡張](vs_scalingexistingclusters.html)
* [コンソール以外で作成されたクラスターの拡張](vs_orderingforclustersoutside.html)
