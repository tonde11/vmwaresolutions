---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-15"

---

# HA クラスターを追加するときに vSphere コンソールに構成の問題が表示される

## 問題
ファイル共有が 1 つだけの HA (高可用性) クラスター構成を追加すると、次の構成上の問題が ESXi ホストに表示されます。

`The number of heartbeat datastores for host is 1, which is less than required: 2`

## 解決方法
この問題は、共有ストレージが冗長化されていないためにデータ・ストアのハートビートを実行できない場合に発生します。

詳細と問題解決手順については、[HA error: "The number of heartbeat datastores for host is 1, which is less than required: 2" (2004739)](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2004739) を参照してください。
