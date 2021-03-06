---

copyright:

  years:  2016, 2018

lastupdated: "2018-07-24"

---

# Cloud Foundation インスタンスに関するネットワーキングの考慮事項

Cloud Foundation インスタンスに関するネットワーキングの考慮事項と要件について詳しくは、以下の情報を確認してください。 インスタンスが正常に機能するように、要件を満たしていることを確認してください。

## Cloud Foundation インスタンスに関するネットワーキング・コンポーネント

Cloud Foundation インスタンス内に組み込まれているネットワーキング・コンポーネントを確認するには、[Cloud Foundation インスタンスの技術仕様](sd_cloudfoundationoverview.html#technical-specifications-for-cloud-foundation-instances)を参照してください。

## NSX ファイアウォールに関する考慮事項

NSX Distributed Firewalls (DFW) を使用している場合、すべてのプロトコルが IP アドレス `10.0.0.0/8` と `161.26.0.0/16` 上で通信できるように、{{site.data.keyword.IBM}} CloudDriver 仮想サーバー・インスタンス (VSI) と SDDC Manager 仮想マシン (VM) からのすべての通信に関してルールを構成する必要があります。

## VM での VMware NSX の使用

Cloud Foundation インスタンスのデプロイ時に、インスタンス内で VMware NSX の注文、インストール、ライセンス交付、構成が行われます。 また、NSX Manager、NSX Controllers、および NSX Transport Zone がセットアップされ、各 ESXi サーバーに NSX コンポーネントが構成されます。

しかし、ワークロード VM が相互に通信したりインターネットにアクセスしたりする必要がある場合は、VM で使用できる NSX をユーザーの責任で構成する必要があります。

NSX のセットアップ方法に関する情報:
* 1 次 (単一) Cloud Foundation インスタンスの場合、[Setting up NSX for workload VMs on VMware Cloud Foundation on {{site.data.keyword.cloud_notm}}](https://developer.ibm.com/recipes/tutorials/setting-up-nsx-for-workload-vms-on-vmware-cloud-foundation-on-ibm-cloud-vcf/) を参照してください。
* マルチサイト Cloud Foundation インスタンスの場合、[Securely connect your private VMware workloads in the {{site.data.keyword.cloud_notm}}](https://www.ibm.com/developerworks/library/se-securely-connect-private-vmware-workloads-ibm-cloud/index.html) を参照してください。

## NSX コンポーネントのパスワードを変更する際の考慮事項

NSX Manager、NSX Controllers、NSX Edge のパスワードを変更する場合は、その前に以下の考慮事項を確認してください。
* NSX Manager のパスワードは変更しないでください。 このパスワードは、{{site.data.keyword.vmwaresolutions_short}} コンソール内のインスタンスの**「サマリー」**ページにあります。
* NSX Controller のパスワードは変更できます。 NSX Controller のパスワードを変更する方法については、[コントローラ パスワードの変更](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx.admin.doc/GUID-2667DD9E-E2F5-4403-BAC2-C7D1BBC23228.html)を参照してください。
* 管理 VMware NSX Edge Services Gateway (ESG) のパスワードは変更しないでください。

### 関連リンク

* [NSX の概要](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx-cross-vcenter-install.doc/GUID-10944155-28FF-46AA-AF56-7357E2F20AF4.html){:new_window}
* [NSX Edge Services Gateway](https://www.ibm.com/cloud/garage/architectures/implementation/virtualization_nsx){:new_window}
* [NAT ルールの管理](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx.admin.doc/GUID-5896D8CF-20E0-4691-A9EB-83AFD9D36AFD.html){:new_window}
