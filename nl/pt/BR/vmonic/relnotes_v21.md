---

copyright:

  years:  2016, 2018

lastupdated: "2018-04-16"

---

# Notas sobre a liberação para V2.1

Esta liberação inclui novos recursos, atualizações de componentes, aprimoramentos de usabilidade e correções de bug. Para obter uma lista de problemas corrigidos em liberações diferentes, problemas conhecidos com o produto e dicas adicionais para usar o {{site.data.keyword.vmwaresolutions_full}}, veja o [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## Correção para Spectre e Meltdown

O {{site.data.keyword.vmwaresolutions_short}} liberou correções do VMware em resposta às vulnerabilidades conhecidas como Spectre e Meltdown (CVE-2017-5753, CVE-2017-5715 e CVE-2017-5754).

* CVEID: [CVE-2017-5753](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753)
* CVEID: [CVE-2017-5715](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715)
* CVEID: [CVE-2017-5754](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754)

Para obter mais informações, veja [Tratando as vulnerabilidades Spectre e Meltdown](../vmonic/trbl_fix_spectre.html).

## VMware HCX on IBM Cloud

O serviço HCX on {{site.data.keyword.cloud_notm}} está disponível para instâncias do VMware Cloud Foundation e do VMware vCenter Server que estão executando o vSphere 6.5 e que são implementadas em ou têm upgrade feito para a V2.1 ou liberações mais recentes. Esse serviço pode ampliar continuamente as redes de seus data centers locais no {{site.data.keyword.cloud_notm}}, que permite a migração bidirecional de máquinas virtuais (VMs) entre os data centers locais e o {{site.data.keyword.cloud_notm}} sem nenhuma mudança. Ao estabelecer uma ponte de camada 2, o HCX alavanca a otimização, deduplicação, compactação e criptografia WAN para migrar com mais rapidez e segurança os dados em um túnel do Direct Link ou VPN. A migração em massa de VMs é compatível com versões anteriores com o VMware vSphere 5.1 ou superior. Se você usar o vSphere 6.0 ou superior no local, será possível efetuar vMotion em tempo real (ligado) em VMs do local para um {{site.data.keyword.CloudDataCent_notm}}. Não é necessário ter o VMware NSX instalado em seu data center ao usar o HCX.

É possível pedir instâncias do Cloud Foundation ou do vCenter Server com o serviço HCX on {{site.data.keyword.cloud_notm}} incluído quando você pede a sua instância ou incluir esse serviço em suas instâncias existentes posteriormente na guia **Serviços** na página de detalhes da instância.

É possível também pedir uma instância do HCX local para licenciamento e ativação da instalação do HCX local.

Para obter mais informações, veja os tópicos a seguir:
* [Considerações para o HCX no {{site.data.keyword.cloud_notm}}](../services/hcx_considerations.html)
* [Gerenciando o HCX no {{site.data.keyword.cloud_notm}}](../services/managinghcx.html)
* [Considerações para instâncias do HCX locais](../services/standalone_considerations.html)
* [Pedindo instâncias do HCX locais](../services/standalone_orderingserviceinstances.html)

## Modelo mais flexível do Bring Your Own License para o VMware Cloud Foundation e o vCenter Server

O Bring Your Own License (BYOL) ou a compra de um licenciamento de assinatura fornecido pela IBM ao criar um novo cluster está disponível para instâncias do VMware Cloud Foundation V2.1 e mais recente e para instâncias do VMware vCenter Server permitindo que você alavanque a chave de componente existente ou alugue a licença da IBM. Antes da V2.1, não é possível comprar licenciamento fornecido pela IBM para um componente específico do VMware se você BYOL. Nesse momento, apenas o VMware vSphere e o VMware vSAN estão disponíveis para licenciamento por cluster.

Além disso, ao incluir nós em um cluster licenciado com sua chave, o console solicitará que você forneça uma nova chave de licença se o número de nós exceder a capacidade da chave.

Para obter mais informações, veja os tópicos a seguir:

* [Incluindo e visualizando clusters para instâncias do Cloud Foundation](../sddc/sd_addingviewingclusters.html)
* [Incluindo e visualizando clusters para instâncias do vCenter Server](../vcenter/vc_addingviewingclusters.html)
* [Pergunta mais frequente sobre BYOL](../vmonic/faq_byol.html)

## Atualizações de componentes de serviço Zerto on IBM Cloud

Para o serviço Zerto on {{site.data.keyword.cloud_notm}} implementado em instâncias do Cloud Foundation V2.1 e mais recente e em instâncias do vCenter Server, o Zerto Virtual Replication 5.5u2 será fornecido. Agora, os dispositivos de replicação virtual (VRAs) Zerto são implementados no armazenamento de dados de gerenciamento (vSAN ou Endurance) em vez de no armazenamento de dados local por motivos de desempenho. Se você tiver VRAs existentes, deverá considerar migrar seu armazenamento para o armazenamento de dados de gerenciamento para melhor desempenho.

Para obter mais informações, consulte [Visão geral do Zerto on {{site.data.keyword.cloud_notm}}](../services/addingzertodr.html).

## Atualizações para instâncias do VMware vCenter Server

### NetworkMTU as definições de configuração

Para V2.1 ou liberações mais recentes, as novas instâncias do vCenter Server são pedidas com a configuração Distributed Virtual Switch (DVS) público como MTU 1500 (padrão). Para obter mais informações, veja _Definições de configuração de MTU de rede_ em [Lista de materiais do vCenter Server](../vcenter/vc_bom.html).

### Aplicação automática de correções e atualizações do VMware ESXi em hosts

Em instâncias do VMware vCenter Server V2.0 e anterior, as correções não foram aplicadas automaticamente em hosts ESXi que foram incluídos em um cluster.

Em instâncias V2.1 e mais recente, a automação aplica correções a novos hosts ESXi para que o nível de correção corresponda ao nível de correção no momento que a instância inicial foi fornecida. Você é responsável por aplicar manualmente todas as correções e atualizações futuras.
Quando correções e atualizações do VMware se tornam disponíveis em liberações futuras, a automação varre os hosts ESXi das instâncias existentes e envia a você um lembrete por e-mail para aplicar manualmente as correções e atualizações mais recentes.

Para obter mais informações, veja [Aplicando atualizações em instâncias do vCenter Server](../vcenter/vc_applyingupdates.html).

### Estimativas de preço para upgrades de licença do VMware NSX

Agora, é possível ver uma estimativa de preço antes de enviar um pedido para upgrade para o VMware NSX Advanced ou Enterprise Edition. A precificação é baseada no número de hosts ESXi na instância do vCenter Server. Essa compra muda apenas a chave de licença NSX e faz upgrade do VMware NSX Base Edition para o Advanced ou Enterprise Edition. A compra não faz upgrade da versão de software NSX.

Para obter mais informações, veja [Visão geral do vCenter Server](../vcenter/vc_vcenterserveroverview.html).

### O máximo de servidores por cluster aumenta a partir de 32

Para o cluster padrão em uma instância, é possível implementar ou expandir até 51 servidores. Para todos os clusters subsequentes em uma instância, é possível implementar ou expandir até 59 servidores. Para obter mais informações, veja [Incluindo e visualizando clusters para instâncias do vCenter Server](../vcenter/vc_addingviewingclusters.html).

**Nota:** esse recurso está disponível apenas para instâncias implementadas na V2.1 e mais recente. Instâncias que têm upgrade feito para a V2.1 de liberações pré-V2.1 não têm essa funcionalidade.

### Opções de configuração do IBM Cloud Bare Metal Server customizadas pelo usuário

Agora, a configuração de Bare Metal Servers customizada oferece o Dual Intel Xeon Gold 6140 com 36 núcleos no total, 2,3 GHz.

Para obter mais informações, veja os tópicos a seguir:
* [Visão geral do vCenter Server](../vcenter/vc_vcenterserveroverview.html)
* [Pedindo instâncias do vCenter Server](../vcenter/vc_orderinginstance.html)

### Configurações de compartilhamento de arquivos NFS individuais

Você tem a opção de configurar compartilhamentos de arquivos NFS em uma base individual. Selecione o tamanho do arquivo e o nível de desempenho para cada compartilhamento de arquivo individual ou selecione o mesmo tamanho de arquivo e nível de desempenho para todos os compartilhamentos de arquivos que você pedir.

Para obter mais informações, veja os tópicos a seguir:
* [Visão geral do vCenter Server](../vcenter/vc_vcenterserveroverview.html)
* [Pedindo instâncias do vCenter Server](../vcenter/vc_orderinginstance.html)
* [Incluindo e visualizando clusters para instâncias do vCenter Server](../vcenter/vc_addingviewingclusters.html)

## Atualizações e aprimoramentos da interface com o usuário

São feitas melhorias em toda a interface com o usuário:

* A opção **Pedir Instância** foi removida da área de janela de navegação esquerda. Clique em **Introdução** para concluir as etapas para pedir uma instância.
* O campo **Prefixo do Subdomínio** da página **Básico** ao pedir uma instância é renomeado para **Rótulo do Subdomínio**.
* Além de visualizar sua estimativa de custo na página **Resumo** ao pedir uma instância primária ou secundária do vCenter Server ou do Cloud Foundation, é possível calcular uma estimativa de custo em qualquer painel conforme você fornecer os detalhes para seu pedido de instância.
* A navegação de trilha de navegação é incluída na página **Instâncias Implementadas** como um método de navegação alternativo, reduzindo, assim, o número de etapas necessárias para alcançar páginas pai nessas páginas.
* Várias mensagens de erro e aprimoramentos de dica de ferramenta foram feitos para ajudá-lo na seleção da configuração apropriada na interface com o usuário.

## Documentação nova e atualizada

Uma nova orientação do developerWorks está disponível com instruções passo a passo sobre como anexar armazenamento dedicado às implementações existentes do {{site.data.keyword.vmwaresolutions_full}} usando o NetApp ONTAP Select on {{site.data.keyword.cloud_notm}}. Para obter mais informações, veja [Etapas para anexar o armazenamento dedicado ao VMware Solutions on IBM Cloud](https://developer.ibm.com/recipes/tutorials/steps-to-attach-dedicated-storage-to-existing-ic4v-deployments-on-ibm-cloud/).
