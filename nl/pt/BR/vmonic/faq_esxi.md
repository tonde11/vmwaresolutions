---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-14"

---

# Perguntas mais frequentes sobre servidores ESXi

Encontre respostas às perguntas mais frequentes sobre os servidores ESXi gerenciados no console do {{site.data.keyword.vmwaresolutions_full}}.

## Quantos servidores ESXi posso incluir em minha instância?

* Para instâncias do vCenter Server, é possível expandir o cluster padrão para ter até 51 servidores ESXi. Cada um dos clusters não padrão pode ser expandido para ter até 59 servidores ESXi. Como é possível incluir até 10 clusters em uma instância, cada instância implementada pode ter um máximo de 51 + 9x59 = 582 servidores ESXi em todos os clusters.
* Para instâncias do Cloud Foundation, a configuração padrão tem quatro servidores ESXi. É possível incluir um máximo de 28 servidores (para um total de 32 servidores). Para instâncias do Cloud Foundation em uma configuração de vários sites, é possível ter um máximo de 128 servidores ESXi em todas as instâncias.

  **Nota**: se sua configuração do Cloud Foundation exigir uma implementação de vários sites com mais de 128 servidores ESXi, [entre em contato com o Suporte IBM](trbl_support.html) para obter assistência.

## Quantos servidores ESXi posso incluir em um cluster?

Para V2.2 e liberações mais recentes, é possível incluir um máximo de 51 servidores ESXi em um cluster inicial e um máximo de 59 servidores ESXi nos clusters incluídos.

Para instâncias implementadas na V2.1 ou liberações anteriores, deve-se ativar o suporte vSAN necessário para aumentar o tamanho do cluster além de 32. Conclua as etapas a seguir para ativar o suporte vSAN necessário:

1. Em cada servidor ESXi implementado, execute os comandos a seguir:

   `esxcli system settings advanced set -o /VSAN/goto11 -i 1`

   `esxcli system settings advanced set -o /Net/TcpipHeapMax -i 1576`

2. Reinicie cada servidor ESXi. Para obter mais informações, veja [Criando um cluster vSAN 6.x com até 64 hosts](https://kb.vmware.com/s/article/2110081).
3. Talvez seja necessário aumentar o tamanho do vCenter Server para acomodar as máquinas virtuais incluídas e os servidores ESXi.
4. Abra um chamado de suporte IBM para indicar que você aplicou as mudanças no vSAN manualmente, concluindo as etapas de 1 a 3. No chamado, solicite que sua instância atualizada esteja ativada para servidores ESXi além de 32.

## Posso mudar os nomes dos servidores ESXi e endereços IP?

Os nomes do servidor ESXi e os endereços IP não podem ser mudados porque estão registrados para a resolução DNS do Windows. As mudanças podem resultar em falhas durante a implementação ou em falhas de funções do vCenter Server.

**Nota**: não use o recurso **Renomear dispositivo** na interface com o usuário do {{site.data.keyword.cloud_notm}} para mudar os nomes do servidor ESXi. Essa função realmente mudará o FQDN do servidor ESXi, mas o vCenter Center configurado e os registros do host do VSI do Windows estarão incorretos e podem causar falhas.

## Posso desativar o acesso raiz nos meus servidores ESXi?

É recomendável manter o acesso raiz ativado nos servidores ESXi, caso contrário, poderão ocorrer falhas nas funções do {{site.data.keyword.vmwaresolutions_short}}.

Se necessário, é possível desativar o acesso raiz após os servidores ESXi terem um status **Pronto para uso** no console do {{site.data.keyword.vmwaresolutions_short}}.

Deve-se reativar o acesso raiz para operações de automação subsequentes, por exemplo, ao incluir ou remover compartilhamentos de arquivo ou ao instalar serviços complementares, como Zerto on {{site.data.keyword.cloud_notm}}.

## Posso incluir rotas estáticas nos meus servidores ESXi para montar o armazenamento de outros locais?

Rotas estáticas podem ser incluídas para armazenamento, mas as operações devem ser realizadas com extremo cuidado. Caso contrário, os compartilhamentos existentes poderão se tornar desmontados.

**Nota**: a inclusão de rotas estáticas para o vMotion não é suportada. Mudanças na configuração de sub-rede do vMotion poderão resultar em falhas nas funções do {{site.data.keyword.vmwaresolutions_short}}.

### Links relacionados

* [Expandindo e contraindo capacidade para instâncias do vCenter Server](../vcenter/vc_addingremovingservers.html)
* [Expandindo e contraindo capacidade para instâncias do Cloud Foundation](../sddc/sd_addingremovingservers.html)
* [Incluindo, visualizando e excluindo clusters para instâncias do vCenter Server](../vcenter/vc_addingviewingclusters.html)
* [Incluindo, visualizando e excluindo clusters para instâncias do Cloud Foundation](../sddc/sd_addingviewingclusters.html)
* [Entrando em contato com o Suporte IBM](trbl_support.html)
