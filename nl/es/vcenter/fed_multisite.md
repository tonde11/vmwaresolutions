---

copyright:

  years:  2016, 2018

lastupdated: "2018-04-16"

---

# Configuración de varios sitios para instancias de VMware Federal

{{site.data.keyword.vmwaresolutions_full}} permite desplegar instancias en diferentes ubicaciones y conseguir que se activen y se ejecuten en un breve periodo de tiempo.

**Nota:** la configuración de varios sitios para instancias de VMware Federal solo está admitida para instancias de V2.3 y posterior.

## Componentes de un despliegue de varios sitios

Un despliegue de varios sitios consta de los siguientes componentes.

* **Instancia primaria**: la instancia primaria de VMware Federal tiene la siguiente configuración:
  *  Dominio raíz Microsoft Active Directory (AD) y DNS (Sistema de nombres de dominio)
  *  Subdominio de vCenter Server
  *  Dominio SSO (inicio de sesión único)
  *  Nombre del sitio SSO
* **Instancia o instancias secundarias**: una o varias instancias secundarias de VMware Federal, enlazadas a la instancia primaria, con la configuración siguiente:
   *  Nombre del sitio SSO
   *  Subdominio DNS enlazado al dominio raíz en la instancia primaria
   *  Se configura la réplica de DNS y AD entre las máquinas virtuales AD en las instancias primaria y secundarias.
   *  Se despliega y configura un PSC (Platform Services Controller) para realizar réplicas con el PSC en la instancia primaria.
   *  Se configura VMware vCenter en las instancias secundarias con la modalidad de enlace mejorado con el vCenter en la instancia primaria.

## Despliegue de varios sitios de VMware Federal

La característica de configuración de varios sitios utiliza una topología de estrella ("hub and spoke") con un sitio primario y un máximo se siete sitios secundarios. Se da soporte a una sola capa de sitios, es decir, no puede configurar otros sitios enlazados a otros sitios secundarios. Puede tener un total de 128 servidores ESXi en una configuración de varios sitios entre todas las instancias.

**Nota**: si la configuración requiere un despliegue de varios sitios con más de 128 servidores ESXi, póngase en contacto con el equipo de soporte de IBM para obtener ayuda. Para obtener más información, consulte [Cómo ponerse en contacto con el equipo de soporte de IBM](../vmonic/trbl_support.html).

En el siguiente gráfico se muestra una visión general del despliegue de varios sitios de VMware Federal.

Figura 1. Despliegue de varios sitios de VMware Federal

![Despliegue de varios sitios de vCenter Server](../sddc/multisite-hub-spoke.svg)

El modelo contiene las siguientes capas:

* **Instancia primaria**: en una configuración de varios sitios, para desplegar la primera instancia debe definir dicha instancia como primaria durante el proceso de pedido de la instancia.
* **Instancias secundarias**: en una configuración de varios sitios, debe definir las instancias que están conectadas a la instancia primaria como instancias secundarias durante el proceso de pedido.

Las instancias secundarias se asignan a una instancia primara de una en una. Para asignar varias instancias secundarias a una instancia primaria, debe repetir el proceso de solicitud para cada instancia secundaria que desee crear.

Puede tener un máximo de 8 (1 primaria y 7 secundarias) instancias desplegadas en una configuración de varios sitios.

**Nota**: la supresión de instancias de VMware Federal que formen parte de una configuración de varios sitios requiere una planificación especial. Para obtener más información, consulte [Supresión de instancias de VMware Federal en una configuración de varios sitios](fed_deletinginstance_multi.html).

## Enlaces relacionados

* [Asignación del rol primario a NSX Manager](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-44E8AE16-BA3F-4DD9-B582-FC1E137E6CFC.html){:new_window}
* [Configuración de NSX Managers secundarios](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-9E48BC57-15E3-49C7-8BC5-F94ED8918BBE.html){:new_window}
* [AD Trusts reciben soporte con SSO (inicio de sesión único) de vCenter](https://kb.vmware.com/kb/2064250){:new_window}
* [Conexión segura de sus cargas de trabajo privadas de VMware en IBM Cloud](https://www.ibm.com/developerworks/library/se-securely-connect-private-vmware-workloads-ibm-cloud/index.html){:new_window}
