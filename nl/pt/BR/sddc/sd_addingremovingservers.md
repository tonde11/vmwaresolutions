---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-17"

---

# Expandindo e contraindo a capacidade para instâncias do Cloud Foundation

É possível expandir ou contrair a capacidade de sua instância do VMware Cloud Foundation de acordo com as necessidades do negócio, incluindo ou removendo servidores ESXi.

Uma instância do Cloud Foundation pode ter até cinco clusters, um dos quais é o padrão. Cada cluster inicial pode ter até 51 servidores ESXi e clusters adicionais podem ter até 59.

## Incluindo servidores ESXi em instâncias do Cloud Foundation

### Antes de Incluir Servidores ESXi

* Não inclua servidores ESXi do Web client do VMware vSphere. As mudanças que você faz no VMware vSphere Web Client não são sincronizadas com o console do {{site.data.keyword.vmwaresolutions_full}}.
* A plataforma base que você pediu tem 4 servidores ESXi por padrão. É possível expandir a plataforma para no máximo 32 servidores ESXi. No entanto, o número de {{site.data.keyword.baremetal_short}} que você pode incluir de cada vez é o seguinte:
   * Para a configuração **Pequena** e **Grande**, é possível incluir de 1 a 10 servidores ESXi de cada vez.
   * Para a configuração **Customizado**, é possível incluir de 1 a 20 servidores ESXi de cada vez.

## Procedimento para Incluir Servidores ESXi

1. No console do {{site.data.keyword.vmwaresolutions_short}}, clique em **Instâncias implementadas** na área de janela de navegação esquerda.
2. Na tabela **Instâncias do Cloud Foundation**, clique na instância para a qual você deseja expandir a capacidade.
3. Clique em **Infraestrutura** na área de janela de navegação esquerda.
4. Na tabela **CLUSTERS**, clique no cluster no qual você deseja incluir servidores ESXi.
5. Na seção **Servidores ESXi**, clique em **Incluir**.
6. Na janela **Incluir servidor**, insira o número de servidores que deseja incluir, revise o custo estimado e, em seguida, clique em **Incluir**.

### Resultados após a inclusão de servidores ESXi

1. Você pode ter um pequeno atraso no console enquanto o status da instância é mudado de **Pronto para o uso** para **Modificando**. Permita que a operação seja totalmente concluída antes de fazer mudanças adicionais na instância.
2. Você é notificado por e-mail quando seus servidores ESXi são incluídos.
3. Se não vir os novos servidores ESXi incluídos na lista no cluster, verifique as notificações por e-mail ou do console para localizar mais detalhes sobre a falha.

## Removendo servidores ESXi de instâncias do Cloud Foundation

### Antes de remover servidores ESXi

* Não remova servidores ESXi do Web client do VMware vSphere. As mudanças que você faz no VMware vSphere Web Client não são sincronizadas com o console do {{site.data.keyword.vmwaresolutions_short}}.
* A plataforma base que você pediu tem 4 servidores ESXi por padrão. É possível remover os servidores ESXi que você incluiu. Não é possível remover os servidores ESXi padrão.
* Antes de remover servidores do ESXi com o serviço F5 on {{site.data.keyword.cloud_notm}} ou o FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}} instalado, deve-se migrar as VMs do F5 BIG-IP e do FortiGate para um servidor do ESXi diferente daquele que está atualmente hospedando as VMs.
* Antes de remover servidores ESXi com o serviço do IBM Spectrum Protect Plus no {{site.data.keyword.cloud_notm}} instalado, certifique-se de que não haja nenhuma operação ativa (com falha ou em andamento) de backup ou restauração, pois essas operações ativas podem impedir que os servidores ESXi sejam removidos.

## Procedimento para remover servidores ESXi

1. No console do {{site.data.keyword.vmwaresolutions_short}}, clique em **Instâncias implementadas** na área de janela de navegação esquerda.
2. Na tabela **Instâncias do Cloud Foundation**, clique na instância para a qual você deseja contratar capacidade.
3. Clique em **Infraestrutura** na área de janela de navegação esquerda.
4. Na tabela **CLUSTERS**, clique no cluster do qual você deseja remover servidores ESXi.
6. Na seção **Servidores ESXi**, selecione os servidores que você deseja remover e clique em **Remover**.

### Resultados após a remoção de servidores ESXi

1. Você pode ter um pequeno atraso no console enquanto o status da instância é mudado de **Pronto para o uso** para **Modificando**. Permita que a operação seja totalmente concluída antes de fazer mudanças adicionais na instância.
2. Você é notificado por e-mail quando seus servidores ESXi são removidos.
3. Os servidores ESXi são totalmente recuperados pela infraestrutura do {{site.data.keyword.cloud_notm}} no final do ciclo de faturamento do {{site.data.keyword.cloud_notm}}, que geralmente é de 30 dias.

   **Atenção**: você será cobrado até o final do ciclo de faturamento do {{site.data.keyword.cloud_notm}} pelos servidores ESXi removidos.

### Links relacionados

* [Lista de materiais do Cloud Foundation](sd_bom.html)
* [Requisitos e planejamento para instâncias do Cloud Foundation](sd_planning.html)
* [Incluindo, visualizando e excluindo clusters para instâncias do Cloud Foundation](sd_addingviewingclusters.html)
* [Colocar um host no modo de manutenção](http://pubs.vmware.com/vsphere-60/index.jsp?topic=%2Fcom.vmware.vsphere.resmgmt.doc%2FGUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){:new_window}
* [Suporte ao processador Enhanced vMotion Compatibility (EVC)](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1003212){:new_window}
