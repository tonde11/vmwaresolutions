---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-13"

---

# Gerenciamento de infra-estrutura de armazenamento anex

Gerenciamento de infraestrutura refere-se aos componentes do VMware que estão gerenciando a infraestrutura do vSphere ESXi.

Para obter mais informações sobre os componentes, veja a Figura 2. Visão geral da rede do NSX Manager em [Design de infraestrutura virtual](../solution/design_virtualinfrastructure.html).

## Design de rede virtual

A virtualização de rede usada neste design usa o vSphere Distributed Switch (vDS) existente associado à rede privada e especificado na [arquitetura do {{site.data.keyword.vmwaresolutions_full}}](../solution/solution_overview.html).

## Comutador Distribuído do vSphere

Conforme indicado anteriormente, outra VLAN é criada dentro da solução do vCenter Server e usada para conectar o ponto de montagem NFS aos hosts ESXi no cluster existente. Como a solução do vCenter Server já tem um vSphere Distributed Switch (vDS) associado à rede privada, outro grupo de portas é criado e identificado com o número de VLAN adicional, visto que essa VLAN adicional não é nativa.

A tabela a seguir descreve as configurações padrão do novo grupo de portas.

**Importante**: não mude essas configurações padrão.

Tabela 1. Resumo do grupo da porta NFS

| Nome do Grupo da Porta | SDDC-DPG-NFS |
|:--------------- |:------------ |
| Ligação de porta | Estático |
| Tipo de VLAN | VLAN B privada |
| Balanceamento de | Rotear base na porta virtual de origem |
| Uplinks Ativos | Uplink1 e uplink2 |

Além da criação do grupo de portas vDS para tráfego de armazenamento do NFS, uma porta VMkernel é criada em cada host do vSphere ESXi na implementação e designada ao grupo de portas SDDC-DPG-NFS. Um endereço IP também é designado à porta VMkernel por meio da sub-rede móvel privada que está associada à VLAN do armazenamento conectado, ou seja, a VLAN B privada B e sua MTU é configurada como 9000 para suportar quadros gigantes.

Figura 1. Grupos de portas e uplinks do vDS privado

![Grupos de portas e uplinks do vDS privado](private_vds_portgroups_and_uplinks.svg "Grupos de portas e uplinks do vDS privado")

### roteamento estático do host vSphere

Embora o vDS seja configurado com um novo grupo de portas e uma porta VMkernel seja designada ao grupo de portas, a solução cria uma rota estática em cada host do vSphere ESXi na implementação para que todo o tráfego do NFS atravesse a VLAN e a sub-rede para o NFS. A rota estática é criada em `/etc/rc.local.d/local.sh` para que persista em reinicializações do host.

### Links relacionados

* [ Visão geral da solução ](../solution/solution_overview.html)
