---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-15"

---

# 订购 Cloud Foundation 实例

要部署具有标准计算、存储和网络配置的统一软件定义数据中心 (SDDC) 平台，请订购 VMware Cloud Foundation 实例。在初始订购中，还可以添加服务，例如用于灾难恢复的 [Zerto on {{site.data.keyword.cloud}}](../services/addingzertodr.html)。

## 需求

确保已完成以下任务：
*  已在**设置**页面上配置 {{site.data.keyword.cloud_notm}} 基础架构凭证。有关更多信息，请参阅[管理用户帐户和设置](../vmonic/useraccount.html)。
*  已查看[针对 Cloud Foundation 实例的需求和规划](sd_planning.html)中的需求和注意事项。

**重要信息**：不要修改在订购和实例部署期间设置的任何值。这样做可能会导致实例变得不可用。此外，在部署实例之后，不要更改实例名称、根域名、子域标签或主机名前缀。

## 系统设置

订购 Cloud Foundation 实例时，必须指定以下系统设置。

### 实例名称

实例名称必须满足以下需求：
* 只允许使用字母数字字符和短划线 (-) 字符。
* 实例名称必须以字母数字字符开头和结尾。
* 实例名称的最大长度为 10 个字符。
* 实例名称在您的帐户中必须唯一。

### 主实例或辅助实例

选择是订购新的主实例还是为现有主实例订购辅助实例。

## 许可证设置

为实例中的以下 VMware 组件指定许可选项：  
* vCenter Server 许可证 - 标准
* vSphere 许可证 - Enterprise Plus
* NSX 许可证 - Enterprise
* vSAN 许可证：选择 Advanced Edition 或 Enterprise Edition

对于业务合作伙伴用户，会包含 vCenter Server 许可证 (Standard Edition)、vSphere 许可证 (Enterprise Plus Edition)、NSX 许可证和 vSAN 许可证，这些许可证以您的名义购买。但是，您必须指定 vSAN 许可证的版本。

对于非业务合作伙伴用户，可以通过选择**购买时包含**对这些组件使用 IBM 提供的 VMware 许可证，或者可以通过选择**我将提供**并输入您自己的许可证密钥以自带许可证 (BYOL)。

## 裸机服务器设置

### 数据中心位置

选择要托管实例的 {{site.data.keyword.CloudDataCent_notm}}。

### 预配置

选择**预配置**后，无法更改 CPU 或 RAM 设置。

根据需求，选择裸机服务器配置：
  * 小型（双 Intel Xeon E5-2650 V4 / 共 24 个核心，2.2 GHz / 128 GB RAM / 12 个驱动器）
  * 大型（双 Intel Xeon E5-2690 V4 / 共 28 个核心，2.6 GHz / 512 GB RAM / 12 个驱动器）

### 定制

选择**定制**时，可以根据需要选择 CPU 和 RAM 组合。

选择用于裸机服务器的 CPU 型号和 RAM。

表 1. 定制 {{site.data.keyword.baremetal_short}} 的选项

| CPU 模型选项   |RAM 选项|
|:------------- |:------------- |
|双 Intel Xeon E5-2620 V4 / 共 16 个核心，2.1 GHz|128 GB、256 GB、512 GB、768 GB、1.5 TB|
|双 Intel Xeon E5-2650 V4 / 共 24 个核心，2.2 GHz|128 GB、256 GB、512 GB、768 GB、1.5 TB|
|双 Intel Xeon E5-2690 V4 / 共 28 个核心，2.6 GHz|128 GB、256 GB、512 GB、768 GB、1.5 TB|
|双 Intel Xeon Silver 4110 处理器 / 共 16 个核心，2.1 GHz|128 GB、192 GB、384 GB、768 GB、1.5 TB|
|双 Intel Xeon Gold 5120 处理器 / 共 28 个核心，2.2 GHz|128 GB、192 GB、384 GB、768 GB、1.5 TB|
|双 Intel Xeon Gold 6140 处理器 / 共 36 个核心，2.3 GHz|128 GB、192 GB、384 GB、768 GB、1.5 TB|

### 裸机服务器的数量

一个 Cloud Foundation 实例的初始部署中包含 4 个裸机服务器。在下订单时，无法更改裸机服务器数。

## 存储设置

Cloud Foundation 实例仅支持 vSAN 存储器。
* 选择**预配置**裸机服务器配置时，存储设置已标准化且无法更改：
  * 对于**小型**裸机服务器配置，会订购 2 个 1.9 TB SSD SED 磁盘驱动器。
  * 对于**大型**裸机服务器配置，会订购 4 个 3.8 TB SSD SED 磁盘驱动器。
* 选择**定制**裸机服务器配置时，可以通过在 **vSAN 存储器**下指定以下设置来定制实例的 VMware vSAN 存储器：
  * **vSAN 容量磁盘的磁盘类型和大小**：选择满足共享存储器需求的容量。
  * **vSAN 容量磁盘数**：指定要添加的 vSAN 共享存储器的磁盘数。磁盘数量必须为 2、4、6 或 8 个。

## 网络接口设置

订购 Cloud Foundation 实例时，必须指定以下网络接口设置。

### 主机名前缀

主机名前缀必须满足以下需求：
*  只允许使用字母数字字符和短划线 (-) 字符。
*  主机名前缀必须以字母数字字符开头和结尾。
*  主机名前缀的最大长度为 10 个字符。

### 子域标签

子域标签必须满足以下需求：
*  只允许使用字母数字字符和短划线 (-) 字符。
*  子域标签必须以字母数字字符开头和结尾。
*  子域标签的最大长度为 10 个字符。
*  子域标签在您的帐户中必须唯一。

### 域名

根域名必须满足以下需求：
* 域名必须包含两个或更多用句点 (.) 分隔的字符串。
* 第一个字符串必须以字母字符开头并以字母数字字符结尾。
* 除了最后一个字符串外，其他所有字符串都只能包含字母数字和短划线 (-) 字符。
* 最后一个字符串只能包含字母字符。
* 最后一个字符串的长度必须在 2 到 24 个字符范围内。

**注**：主机和 VM（虚拟机）的 FQDN（标准域名）的最大长度为 50 个字符。域名必须符合此最大长度。

### 网络设置的值格式

域名和子域标签用于生成实例的用户名和服务器名称，如下表中所示。

表 2. 用户名、域名和服务器名称的值格式

|名称|值格式|
  |:------------- |:------------- |
  |域名| `<root_domain>` |  
  |标准 ESXi 服务器名称| `<host_prefix><n>.<subdomain_label>.<root_domain>`，其中 `<n>` 是 ESXi 服务器的序列。最大长度为 50 个字符。|   
  |vCenter Server 登录用户名| `<user_id>@<root_domain>`（Microsoft Active Directory 用户）或 `administrator@vsphere.local`|
  |vCenter Server FQDN|`vcenter-1.<subdomain_label>.<root_domain>`. 最大长度为 50 个字符。|  
  |SDDC Manager FQDN|`sddcmanager.<subdomain_label>.<root_domain>`. 最大长度为 50 个字符。|
  |Single Sign-On (SSO) 站点名称| `<subdomain_label>`
  |PSC FQDN|`PSC-<subdomain_label>.<subdomain_label>.<root_domain>`. 最大长度为 50 个字符。|  

  SDDC Manager FQDN 无法公开解析。否则，Cloud Foundation 实例配置可能会失败，并且不可恢复。在指定域名之前，请查看[选择根域名时的注意事项](../vmonic/trbl_limitations.html#considerations-when-choosing-a-root-domain-name-for-cloud-foundation-instances)。

### VLAN

网络设置基于您选择的是**订购新 VLAN** 还是**选择现有 VLAN**。

订购实例时，需要包含一个公用 VLAN 和两个专用 VLAN。两个专用 VLAN 用于中继到每个裸机服务器中。

**订购新的 VLAN**  
选择此项可订购一个新的公用 VLAN 和两个新的专用 VLAN。

**选择现有 VLAN**  
根据选择的 {{site.data.keyword.CloudDataCent_notm}}，可能会有现有公用和专用 VLAN 可用。

选择复用现有公用和专用 VLAN 时，请指定 VLAN 和子网：
  * **公用 VLAN** 用于公用网络访问。
  * **专用 VLAN** 用于连接 {{site.data.keyword.cloud_notm}} 中的各数据中心和服务。
  * **辅助专用 VLAN** 用于 VMware 功能部件，例如 vSAN。
  * **主子网**分配给物理主机以用于公用网络访问。
  * **专用主子网**分配给物理主机以用于管理流量。

**重要信息：**
* 确保所选 VLAN 上的防火墙配置不会阻止管理数据流量。
* 确保选择的所有 VLAN 都在同一 pod 中，因为 ESXi 服务器不能在混合 pod VLAN 上进行供应。

## 服务

订购 Cloud Foundation 实例时，还可以订购更多服务。有关可用服务的更多信息，请参阅 [Cloud Foundation 实例的服务](sd_planning.html#services-for-cloud-foundation-instances)。

## 订单摘要

根据为实例和附加组件服务选择的配置，估算成本会立即生成并显示在右侧窗格中。单击右侧窗格底部的**定价详细信息**可生成提供估算详细信息的 PDF 文档。

## 过程

1. 在 {{site.data.keyword.cloud_notm}}“目录”中，单击左侧导航窗格中的 **VMware**，然后单击**虚拟数据中心**部分中的 **Cloud Foundation**。
2. 在 **VMware Cloud Foundation on IBM Cloud** 页面上，单击**创建**。
3. 在 **Cloud Foundation** 页面上，输入实例名称。
4. 选择实例类型：
   * 单击**主实例**以在环境中部署单个实例，或者在多站点拓扑中部署第一个实例。
   * 单击**辅助实例**以将该实例与环境中的现有（主）实例连接以获取高可用性，并完成以下步骤：
     1. 选择要与辅助实例连接的主实例。
     2. 如果您选择的主实例升级到 V2.5 发行版，或者将主实例部署到或升级到 V2.4 或先前发行版，请检查预填充的**主实例 PSC 的管理员密码**以确保它是正确的。
     
         **注：****主实例 PSC 的管理员密码**字段对于部署在 V2.5 和更高发行版上的主实例不可用。     
5. 完成实例组件的许可证设置：
   *  要使用 IBM 提供的许可证，请选择**购买时包含**。
   *  要使用您自己的许可证，请选择**我将提供**并输入许可证密钥。  
6. 完成裸机服务器设置：
   1. 选择要托管实例的 {{site.data.keyword.CloudDataCent_notm}}。
   2. 选择裸机服务器配置。
      * 选择**预配置**时，请选择**小型**或**大型**配置。
      * 选择**定制**时，请指定 CPU 型号和 RAM 大小。
7. 完成存储设置：
   * 如果对裸机配置选择的是**预配置**，请注意，无法更改**小型**和**大型**标准化裸机服务器配置的存储设置。
   * 如果对裸机配置选择的是**定制**，请指定 **vSAN 容量磁盘的磁盘类型和大小**和 **vSAN 容量磁盘数**。
8. 完成网络接口设置：
   1. 输入主机名前缀、子域标签和根域名。对于辅助实例，系统会自动填写域名。
   2. 选择 VLAN 设置：
      * 如果要订购新的公用和专用 VLAN，请单击**订购新的 VLAN**。
      * 如果要复用可用的现有公用和专用 VLAN，请单击**选择现有 VLAN**，然后指定 VLAN 和子网。

9. 通过单击相应的服务卡，选择要部署到实例中的附加组件服务。如果服务需要配置，请完成特定于服务的设置，然后单击弹出配置窗口中的**添加服务**。有关如何为服务提供设置的信息，请参阅相应的服务订购主题。

10. 在**订单摘要**窗格上，验证实例配置，然后再下订单。
    1. 复查实例的设置。
    2. 复查实例的估算成本。单击**定价详细信息**以生成 PDF 摘要。要保存或打印订单摘要，请单击 PDF 窗口右上角的**打印**或**下载**图标。
    3. 确保要向其收费的帐户正确，然后选中**我了解将向下面列出的帐户收费**复选框。
    4. 单击订单适用条款的链接。确保您同意这些条款，然后选中**我已阅读并同意下面列出的第三方服务协议**复选框。
    5. 单击**供应**。

## 结果

实例部署会自动启动。您将收到说明订单正在处理的确认，并且您可以通过查看实例详细信息来检查部署的状态。

成功部署实例后，[Cloud Foundation 实例的技术规范](../sddc/sd_cloudfoundationoverview.html#technical-specifications-for-cloud-foundation-instances)中描述的组件已安装在 VMware 虚拟平台上。缺省情况下，订购的 ESXi 服务器将分组为 **SDDC-Cluster**。如果订购了更多服务，那么这些服务的部署将在订单完成后启动。

实例准备就绪可供使用后，该实例的状态会更改为**可供使用**，并且您将收到通过电子邮件发送的通知。

订购辅助实例时，在完成辅助实例订单后，可能会重新启动主实例（链接到辅助实例）的 VMware vSphere Web Client。

## 后续步骤

查看和管理订购的 Cloud Foundation 实例。

**重要信息**：您只能在 {{site.data.keyword.vmwaresolutions_short}} 控制台中管理 {{site.data.keyword.cloud_notm}} 帐户中创建的 {{site.data.keyword.vmwaresolutions_short}} 组件，而不能在 {{site.data.keyword.slportal}} 中或在控制台外部通过其他任何方法来进行管理。如果在 {{site.data.keyword.vmwaresolutions_short}} 控制台外部更改这些组件，那么这些更改与控制台不同步。

**注意**：在 {{site.data.keyword.vmwaresolutions_short}} 控制台外部管理任何 {{site.data.keyword.vmwaresolutions_short}} 组件（在订购实例时安装到 {{site.data.keyword.cloud_notm}} 帐户中）可能会使环境变得不稳定。这些管理活动包括：

*  添加、修改、返回或除去组件
*  通过添加或除去 ESXi 服务器来扩展或收缩实例容量
*  关闭组件电源
*  重新启动服务

   这些活动的例外情况包括在 {{site.data.keyword.slportal}} 中管理共享存储器文件共享。此类活动包括：订购、删除（如果已安装，可能会影响数据存储）、授权和安装共享存储器文件共享。

### 相关链接

* [注册 {{site.data.keyword.cloud_notm}} 帐户](../vmonic/signing_softlayer_account.html)
* [查看 Cloud Foundation 实例](sd_viewinginstances.html)
* [添加、查看和删除 Cloud Foundation 实例的集群](sd_addingviewingclusters.html)
* [扩展和收缩 Cloud Foundation 实例的容量](sd_addingremovingservers.html)
* [订购、查看和除去 Cloud Foundation 实例的服务](sd_addingremovingservices.html)
* [删除 Cloud Foundation 实例](sd_deletinginstance.html)
* [关于 BYOL 的常见问题](../vmonic/faq_byol.html)
