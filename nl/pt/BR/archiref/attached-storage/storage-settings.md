---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-17"

---

# Configurações de armazenamento

Esse design suporta a conexão de armazenamento compartilhado via NFS v3 e NFS v4.1 (o NFS v4 não é suportado). Depois de pedir o VMware vCenter Server on {{site.data.keyword.cloud}}, determine qual versão do NFS será usada para o ambiente.

Embora o NFS v4.1 apresente melhor desempenho e disponibilidade por meio do balanceamento de carga e de caminhos múltiplos, ele restringe a utilização dos recursos do vSphere, incluindo o Storage DRS, o Storage I/O Control e o uso do Site Recovery Manager.

A tabela a seguir lista os protocolos do NFS e o suporte para recursos do vSphere ao usar o vSphere 6.0.

Tabela 1. Protocolos do NFS e recursos do vSphere

| Recurso vSphere | NFS v3 | NFS v4.1 |
|:--------------- |:------ |:-------- |
| vMotion vMotion e vMotion | Sim | Sim |
| Alta Disponibilidade (HA) | Sim | Sim |
| Tolerância a Falhas (FT) | Sim | Sim |
| DRS (Distributed Resource Scheduler) | Sim | Sim |
| Perfis do Host | Sim | Sim |
| Storage DRS | Sim | Não |
| Controle de E/S de Armazenamento (SIOC) | Sim | Não |
| Gerenciador de Recuperação do | Sim | Não |
| Volumes Virtuais | Sim | Não |

**Nota**: todo o armazenamento conectado para esse design está limitado ao armazenamento do {{site.data.keyword.cloud_notm}} disponível no mesmo {{site.data.keyword.CloudDataCent_notm}} que a solução do vCenter Server. Além disso, os armazenamentos de dados do NFS v3 e 4.1 montados usando a mesma versão de NFS em todos os hosts e todos os discos virtuais armazenados no armazenamento de dados são thin-provisioned por padrão.

## Usando o NFS v3 para armazenamento conectado

Quando o NFS v3 é escolhido como o método preferencial para conectar o compartilhamento de NFS, a arquitetura é tal que usa um único endereço IP do armazenamento do {{site.data.keyword.cloud_notm}} para se conectar ao compartilhamento. Além disso, o compartilhamento de NFS é conectado a todos os hosts no cluster do vCenter Server e colocado em um cluster de armazenamento de dados com o Storage DRS ativado.

### vSphere Storage Distributed Resource Scheduler (Storage DRS)

O Storage DRS permite gerenciar os recursos agregados de um cluster de armazenamento de dados. Quando o Storage DRS está ativado, ele fornece recomendações para posicionamento e migração de disco da máquina virtual (VM) para equilibrar o espaço e os recursos de E/S nos armazenamentos de dados no cluster de armazenamento de dados.

Os recursos a seguir estão disponíveis quando o Storage DRS está ativado:
* Balanceamento de carga de espaço entre armazenamentos de dados em um cluster de armazenamento de dados
* Balanceamento de carga de E/S entre armazenamentos de dados dentro de um cluster de armazenamento de dados
* Local inicial para discos virtuais com base no espaço e na carga de trabalho de E/S.

Nesse design, o Storage DRS é ativado com o nível de automação configurado como "Totalmente automatizado". Como resultado, os arquivos não são migrados automaticamente para otimizar o uso de recursos no cluster de dados. Observe que todas as outras opções do Storage DRS são configuradas como "Usar configurações do cluster", já que o cluster é totalmente automatizado.

### Configurações de tempo de execução do Storage DRS para o NFS v3

A agressividade do Storage DRS é determinada ao especificar limites para o espaço usado e a latência de E/S. O Storage DRS coleta informações de uso do recurso para os armazenamentos de dados em um cluster de armazenamento de dados. O vCenter Server usa essas informações para gerar recomendações para o posicionamento de discos virtuais em armazenamentos de dados.

Quando o baixo nível de agressividade for configurado para um cluster de armazenamento de dados, o Storage DRS recomendará migrações do Storage vMotion somente quando necessário, por exemplo, se a carga de E/S, a utilização de espaço ou seu desequilíbrio for alto. Quando o alto nível de agressividade for configurado para um cluster de armazenamento de dados, o Storage DRS recomendará migrações sempre que o cluster de armazenamento de dados puder se beneficiar do espaço ou do balanceamento de carga de E/S.

As categorias de limite a seguir estão disponíveis no cluster de armazenamento de dados:

* Utilização de espaço: o Storage DRS gera recomendações ou executa migrações quando a porcentagem de utilização de espaço no armazenamento de dados é maior que o limite configurado no vSphere Web Client.
* Latência de E/S: o Storage DRS gera recomendações ou executa migrações quando a latência de E/S do 90º percentil medida ao longo de um dia para o armazenamento de dados é maior que o limite.

Nesse design, as Configurações de tempo de execução do Storage DRS são ativadas e os limites são mantidos em seus respectivos valores padrão. É altamente recomendável mudar esses valores com base nos requisitos de E/S da carga de trabalho e na sensibilidade de latência.

A tabela a seguir mostra as configurações no VMware vSphere Web Client.

Tabela 2. Configurações de tempo de execução do DRS

| Configuração       | Valor  |
|:--------------- |:------ |
| Ativar métrica de E/S para recomendações do SDRS | Selecionada |
| Espaço Utilizado | Selecionado, configurado como 80% |
| Limite de latência de E/S | 15 ms |

Para obter mais informações sobre como configurar essas definições no vSphere Web Client, consulte [Configurar regras de tempo de execução do Storage DRS no vSphere Web Client](https://docs.vmware.com/en/VMware-vSphere/5.5/com.vmware.vsphere.resmgmt.doc/GUID-AD2D13CE-539B-48C3-BBC9-E55A834874F0.html).

### Controle de E/S de Armazenamento para NFS v3

Quando o SIOC é ativado no ambiente, ele muda o comprimento da fila de dispositivo para a única VM. A mudança para o comprimento da fila de dispositivo reduz a fila de matriz de armazenamento de todas as VMs para um compartilhamento e regulador iguais da fila de armazenamento. O SIOC é encaixado somente se os recursos são restritos e a latência de E/S de armazenamento está acima de um limite definido.

Para que o SIOC determine quando um dispositivo de armazenamento está congestionado ou restrito, ele requer um limite definido. A latência de limite de congestionamento é diferente para tipos de armazenamento diferentes. Esse design recomenda e implementa uma latência de limite de 10 milissegundos.

Também é possível limitar discos virtuais individuais para VMs individuais ou conceder a eles compartilhamentos diferentes com SIOC. A limitação de discos e a concessão de compartilhamentos diferentes permite que você corresponda e alinhe o ambiente à carga de trabalho com o número de IOPS do volume de armazenamento de arquivo adquirido. O limite é configurado por IOPS e é possível configurar um peso diferente ou "Compartilhamentos".

Os compartilhamentos de discos virtuais configurados como "Alto" (2.000 compartilhamentos) recebem o dobro de E/S que um disco configurado como "Normal" (1.000 compartilhamentos) e quatro vezes mais que um configurado como "Baixo" (500 compartilhamentos). Normal é o valor padrão para todas as VMs, portanto, é necessário ajustar os valores acima ou abaixo de "Normal" para as VMs que o requerem.

### Armazenamento adicional para NFS v3

Quando surge a necessidade de incluir armazenamento adicional no ambiente devido a espaço insuficiente ou alta latência, é possível pedir outro compartilhamento de NFS por meio do console. Depois que o compartilhamento é pedido, a automação anexa a exportação aos hosts do vSphere ESXi no cluster e a coloca no cluster de armazenamento mencionado anteriormente. Colocar o novo compartilhamento de NFS no cluster de armazenamento dimensiona de forma eficiente e uniforme o armazenamento que está associado ao ambiente sem sobrecarregá-lo com migrações no nível de armazenamento.

## Usando o NFV v4.1 para armazenamento conectado

Quando o NFS v4.1 é escolhido como o método preferencial para conectar o compartilhamento de NFS, a arquitetura é tal que usa vários endereços IP do armazenamento do {{site.data.keyword.cloud_notm}} para se conectar ao compartilhamento. Embora o compartilhamento seja conectado a todos os hosts no cluster do vCenter Server, ele não é colocado em um cluster de armazenamento de dados devido à limitação do vSphere em usar o Storage DRS com o NFS v4.1.

**Nota**: o NFS 4.1 com o vSphere 6.0 não suporta a aceleração de hardware. Essa limitação não permite a criação de discos virtuais espessos em armazenamentos de dados do NFS v4.1.

### Armazenamento Adicional para NFV v4.1

Quando surge a necessidade de incluir armazenamento adicional no ambiente devido a espaço insuficiente ou alta latência, é possível pedir outro compartilhamento de NFS por meio do console. Depois que o compartilhamento é pedido, a automação anexa a exportação aos hosts do vSphere ESXi no cluster. Em seguida, deve-se migrar as VMs e balancear a carga dos armazenamentos de dados para que o espaço seja usado adequadamente e os requisitos de latência sejam atendidos.

## Parâmetros de Configuração Avançados

Independentemente de você escolher o NFS v3 ou o NFS v4.1, esse design inclui parâmetros de configuração avançados recomendados pelo {{site.data.keyword.cloud_notm}}. Como resultado, os parâmetros a seguir são configurados em cada host do vSphere ESXi que está conectado ao compartilhamento de NFS do {{site.data.keyword.cloud_notm}}.

Tabela 3. Parâmetros de Configuração Avançada do NFS

| Parâmetro       | Valor  |
|:--------------- |:------ |
| Net.TcpipHeapSize | 32 |
| Net.TcpipHeapMax | 512 |
| NFS.MaxVolumes | 256 |
| NFS.HeartbeatMaxFailures | 10 |
| NFS.HeartbeatFrequency  | 12 |
| NFS.HeartbeatTimeout | 5 |
| NFS.MazQueueDepth | 64 |

### Links relacionados

* [ Visão geral da solução ](../solution/solution_overview.html)
