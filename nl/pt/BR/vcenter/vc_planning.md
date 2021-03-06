---

copyright:

  years:  2016, 2018

lastupdated: "2018-07-19"

---

# Requisitos e planejamento para instâncias do vCenter Server

Revise os seguintes requisitos antes de pedir suas instâncias do VMware vCenter Server. Planeje sua instância com base no {{site.data.keyword.CloudDataCent}} local, nos requisitos de capacidade de carga de trabalho e nos requisitos de serviço adicionais.

## Requisitos da conta do IBM Cloud

A conta do {{site.data.keyword.cloud_notm}} que você está usando deve atender a determinados requisitos. Para obter mais informações, veja [Requisitos para a conta do {{site.data.keyword.cloud_notm}}](../vmonic/slaccountrequirement.html).

## Disponibilidade do data center do IBM Cloud

A implementação do vCenter Server tem requisitos rigorosos na infraestrutura física. Portanto, é possível implementar instâncias apenas em {{site.data.keyword.CloudDataCents_notm}} que atendam aos requisitos. Os {{site.data.keyword.CloudDataCents_notm}} a seguir estão disponíveis para implementação do vCenter Server:

Tabela 1. {{site.data.keyword.CloudDataCents_notm}} disponível para instâncias do vCenter Server

| {{site.data.keyword.CloudDataCent_notm}} | Localização | Região | Opções do servidor |
|:----------------------|:---------|:-------|:---------------|
| AMS03 | Amsterdã | Europa | Customizado |
| CHE01 | Chennai | Ásia Pacífico | Customizado |
| DAL09 | Dallas | NA Sul | Customizado |
| DAL10 | Dallas | NA Sul | Customizado, Pequeno, Médio, Grande |
| DAL12 | Dallas | NA Sul | Customizado |
| DAL13 | Dallas | NA Sul | Customizado |
| FRA02 | Frankfurt | Europa | Customizado, Pequeno, Médio, Grande |
| FRA04 | Frankfurt | Europa | Customizado |
| HKG02 | Hong Kong | Ásia Pacífico | Customizado |
| LON02 | Londres | Europa | Customizado |
| LON04 | Londres | Europa | Customizado |
| LON06 | Londres | Europa | Customizado, Pequeno, Médio, Grande |
| MEL01 | Melbourne | Ásia Pacífico | Customizado |
| MEX01 | Querétaro | NA Sul | Customizado |
| MIL01 | Milão | Europa | Customizado |
| MON01 | Montreal | NA Leste | Customizado |
| OSL01 | Oslo | Europa | Customizado |
| PAR01 | Paris | Europa | Customizado |
| SAO01 | São Paulo | América do Sul | Customizado |
| SEO01 | Seul | Ásia Pacífico | Customizado |
| SJC03 | São José | Oeste ND | Customizado, Pequeno, Médio, Grande |
| SJC04 | São José | Oeste ND | Customizado |
| SNG01 | Cingapura | Ásia Pacífico | Customizado |
| SYD01 | Sydney | Ásia Pacífico | Customizado |
| SYD04 | Sydney | Ásia Pacífico | Customizado |
| TOK02 | Tóquio | Ásia Pacífico | Customizado |
| TOR01 | Toronto | NA Leste | Customizado, Pequeno, Médio, Grande |
| WDC04 | Washington, DC | NA Leste | Customizado, Pequeno, Médio, Grande |
| WDC06 | Washington, DC | NA Leste | Customizado |
| WDC07 | Washington, DC | NA Leste | Customizado |

Um pequeno subconjunto de {{site.data.keyword.CloudDataCents_notm}} oferece as opções pré-configuradas **Pequeno**, **Médio** e **Grande** do Bare Metal Server. Dependendo da disponibilidade e do fornecimento do inventário, o {{site.data.keyword.CloudDataCents_notm}} pode exibir um indicador de status no console do {{site.data.keyword.vmwaresolutions_short}} para ajudá-lo a planejar suas implementações.

Tabela 2. Indicadores de status para {{site.data.keyword.CloudDataCents_notm}} ao pedir instâncias do vCenter Server

| Status | Detalhes do status |
|:------------------------------|:--------------------------------------------------|
| Em breve                   | O {{site.data.keyword.CloudDataCent_notm}} não está disponível atualmente. |
| Provisoriamente fora do inventário  | O {{site.data.keyword.CloudDataCent_notm}} não possui disponibilidade neste momento. |
| Inventário limitado             | O {{site.data.keyword.CloudDataCent_notm}} limitou a disponibilidade e o pedido pode não estar concluído. |

## Backup de componentes de gerenciamento

Você é responsável por manter e assegurar a disponibilidade de todos os componentes da instância. É altamente recomendável planejar o backup ou a alta disponibilidade de todos os componentes de gerenciamento. Para obter mais informações, consulte [Fazendo backup de componentes](../archiref/solution/solution_backingup.html).

## Serviços para instâncias do vCenter Server

É possível pedir serviços complementares para a sua instância com base em suas necessidades, por exemplo, recuperação de desastre. Para obter mais informações, veja [Pedindo, visualizando e removendo serviços para instâncias do vCenter Server](vc_addingremovingservices.html).

## Considerações sobre capacidade

Para obter informações e considerações de capacidade, consulte [Capacidade de ajuste de escala](../archiref/solution/solution_scaling.html).

### Links relacionados

* [Visão geral do vCenter Server](vc_vcenterserveroverview.html)
* [Pedindo instâncias do vCenter Server](vc_orderinginstance.html)
* [Expandindo e contraindo capacidade para instâncias do vCenter Server](vc_addingremovingservers.html)
* [Pedindo, visualizando e removendo serviços para instâncias do vCenter Server](vc_addingremovingservices.html)
