---

copyright:

  years:  2016, 2018

lastupdated: "2018-07-24"

---

# Zerto on IBM Cloud 관리

Zerto on {{site.data.keyword.cloud}} 서비스가 인스턴스에 배치된 후 Zerto Virtual Replication을 구성하거나 업데이트하고 추가 Virtual Replication Appliances를 새로 추가된 ESXi 서버에 배치할 수 있습니다.

## Zerto용 고유한 인증서 사용

우수 사례로서, ZVM(Zerto Virtual Manager)용 고유한 SSL 인증서를 사용해야 합니다. [How to use a CER SSL Certificate to Replace the Self-Signed Certificate for the ZVM, ZSSP, or ZCM](https://www.zerto.com/myzerto/knowledge-base/how-to-use-a-cer-ssl-certificate-to-replace-the-self-signed-certificate-for-the-zvm-zssp-or-zcm/){:new_window}의 지시사항에 따라 Zerto on {{site.data.keyword.cloud_notm}}를 배치한 후 ZVM용 SSL 인증서를 고유한 인증서로 대체해야 합니다.

## Zerto 복제의 구성 관리

Zerto 복제의 구성(예: 가상 머신을 복제하기 위한 Zerto 인스턴스 다시 페어링 또는 가상 보호 그룹 구성)을 관리하려면 관리자 권한으로 vCenter 인증서를 사용하여 Zerto Virtual Replication 콘솔에 로그인하십시오.

서로 다른 {{site.data.keyword.cloud_notm}} Zerto 인스턴스 간에 복제하는 경우 Zerto 인스턴스 간의 복제를 직접 구성할 수 있습니다. {{site.data.keyword.cloud_notm}} Zerto 인스턴스와 고유한 데이터 센터 간을 복제하는 경우 고유한 데이터 센터에서 Zerto를 자체적으로 설치해야 합니다. 고유한 데이터 센터에 설치하는 Zerto의 인스턴스는 {{site.data.keyword.cloud_notm}} Zerto 인스턴스와 페어링할 때 라이센스를 자체적으로 자동 부여할 수 있습니다.

Zerto 복제가 NAT(Network Address Translation) 순회를 지원하지 않으므로, {{site.data.keyword.cloud_notm}} Zerto 인스턴스와 고유한 데이터 센터 간의 연결을 설정하려면 양쪽의 ZVM(Zerto Virtual Manager) 어플라이언스 또는 Zerto VRA(Virtual Replication Appliances)에서 라우트의 사용자 정의가 필요하고 사이트 간에 보안 터널링도 필요할 수 있습니다. ZVM 어플라이언스에서 라우트를 구성하거나 재구성하는 경우 사용 보고를 위해 모든 ZVM 어플라이언스가 `zerto.com`에 연결해야 합니다. ZVM 어플라이언스에서 `https://www.zerto.com`에 대한 브라우저 세션을 열어 이 연결을 확인할 수 있습니다.

**참고**: {{site.data.keyword.cloud_notm}}에서 Cloud Foundation 인스턴스 및 vCenter Server 인스턴스의 관리 VMware NSX Edge Services Gateway(ESG)가 ZVM에서 시작된 아웃바운드 HTTPS(TCP 포트 443) 통신을 허용하도록 사전 구성되었습니다.

## Zerto Virtual Replication 업데이트

Zerto Virtual Replication을 업데이트하려면 Zerto Virtual Replication 콘솔에 로그인하십시오.

## 새로 추가된 ESXi 서버에 VRA 배치

인스턴스의 기본 클러스터에 대한 ESXi 서버를 추가하거나 제거하는 경우 VRA가 자동으로 배치되거나 제거됩니다. VRA가 인스턴스의 보조 클러스터에 있는 ESXi 서버에 자동으로 배치되지 않지만 Zerto Virtual Replication 콘솔에서 자체적으로 배치할 수 있습니다.

### 관련 링크

* [Zerto on {{site.data.keyword.cloud_notm}} 개요](addingzertodr.html)
* [Zerto on {{site.data.keyword.cloud_notm}}에 대한 관리 서비스 요청](managing_zerto_services.html)
* [zerto.com 웹 사이트](https://www.zerto.com){:new_window}
* [Zerto 기술 문서](https://www.zerto.com/myzerto/technical-documentation/){:new_window}
* [Zerto 재해 복구](https://www.ibm.com/cloud/garage/architectures/virtualizationArchitecture/zerto){:new_window}
* [Zerto Virtual Replication Alerts의 설명](https://www.zerto.com/myzerto/knowledge-base/explanation-of-zvr-alerts/)
