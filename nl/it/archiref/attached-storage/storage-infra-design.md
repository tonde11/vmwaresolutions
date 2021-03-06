---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-14"

---

# Progettazione dell'infrastruttura di archiviazione collegata

{{site.data.keyword.vmwaresolutions_full}} fornisce la tecnologia VMware che viene distribuita in modo automatizzato all'interno dei {{site.data.keyword.CloudDataCents_notm}} in tutto il mondo. Nel portfolio di soluzioni {{site.data.keyword.cloud_notm}}, l'offerta VMware vCenter Server on {{site.data.keyword.cloud_notm}} d base consiste in un massimo di 20 host vSphere, un singolo PSC (Platform Services Controller) e una vCenter Server Appliance in grado di gestire fino a 100 host e 1000 macchine virtuali.

L'architettura qui presentata integra la soluzione vCenter Server aggiungendo l'archiviazione collegata come un dispositivo di archiviazione condivisa per l'ambiente. Il dispositivo di archiviazione collegato si trova nello stesso {{site.data.keyword.CloudDataCent_notm}} della distribuzione del vCenter Server e consiste in una singola condivisione NFS (Network File System) o più esportazioni NFS da {{site.data.keyword.cloud_notm}}.

Il seguente grafico illustra l'architettura generale della distribuzione NetApp ONTAP Select su vCenter Server.

Figura 1. Architettura di alto livello di NetApp ONTAP Select on {{site.data.keyword.cloud_notm}}

![Architettura di NetApp ONTAP Select](../../netapp/np_architecture.svg "Architettura di alto livello di NetApp ONTAP Select on IBM Cloud")

## Progettazione dell'infrastruttura fisica

L'infrastruttura fisica è costituita da tre componenti principali, compresi il calcolo fisico, l'archiviazione fisica e la rete fisica. Ciò include la rete dei servizi {{site.data.keyword.cloud_notm}} e l'archiviazione fisica utilizzata dall'infrastruttura.

## Progettazione della rete fisica

La rete fisica è gestita da {{site.data.keyword.cloud_notm}}. Questa sezione descrive la rete fisica fornita da {{site.data.keyword.cloud_notm}} come si correla all'archiviazione collegata.

### Panoramica della rete di IBM Cloud

La rete fisica di {{site.data.keyword.cloud_notm}} è suddivisa in tre reti distinte: Pubblica, Privata e di Gestione. Per ulteriori informazioni sulle reti pubbliche, private e di gestione, vedi [Panoramica della soluzione](../solution/solution_overview.html).

Per ulteriori informazioni sulla rete {{site.data.keyword.cloud_notm}}, vedi [The {{site.data.keyword.cloud_notm}} network](https://www.ibm.com/cloud-computing/bluemix/our-network){:new_window}.

Esamina le seguenti informazioni per una descrizione della rete dei servizi che fa parte della rete privata.

### Rete dei servizi privata

{{site.data.keyword.cloud_notm}} contiene una rete dei servizi privati che fornisce servizi comuni quali l'archiviazione blocchi, l'archiviazione file, l'archiviazione oggetti, i resolver DNS e i server NTP. Questa rete privata è separata dalla rete privata del cliente e consente agli ambienti di connettersi senza soluzione di continuità ai servizi che si trovano in {{site.data.keyword.cloud_notm}}. La rete privata è multilivello in quanto i server ed altra infrastruttura sono connessi a switch BCS (back-end customer switch) aggregati. Questi switch aggregati sono collegati a una coppia di router separati, ossia BCR (back-end customer router), per la rete L3. La rete privata supporta anche la possibilità di utilizzare i frame Jumbo, ossia MTU 9000, per connessioni all'host fisico.

### VLAN

Per ulteriori informazioni sulle VLAN, vedi la sezione _Progettazione della rete fisica_ in [Progettazione dell'infrastruttura fisica](../solution/design_physicalinfrastructure.html).

## Progettazione dell'archiviazione fisica

Questa sezione presenta la configurazione del dispositivo di archiviazione collegato che è presente in {{site.data.keyword.cloud_notm}}. Il dispositivo di archiviazione collegato integra la soluzione vCenter Server esistente. Di conseguenza, i dischi collegati localmente che sono interni agli host fisici non vengono presentati.

## Prestazioni dell'archiviazione collegata

Le archiviazioni Performance e Endurance sono soluzioni di archiviazione {{site.data.keyword.cloud_notm}} progettate per supportare applicazioni ad elevato I/O che richiedono dei livelli prevedibili di prestazioni. Queste prestazioni prevedibili vengono raggiunte tramite l'assegnazione di IOPS (input/output operations per second) a livello di protocollo ai singoli volumi.

È possibile eseguire il provisioning di un IOPS che va da 100 a 48.000 con delle dimensioni dell'archiviazione che vanno da 20 GB a 12 TB. I volumi di archiviazione Performance ed Endurance sono disponibili sia per l'archiviazione blocchi che per l'archiviazione file.

In questa progettazione la soluzione vCenter Server offre l'archiviazione Endurance per l'archiviazione collegata. Di conseguenza, puoi selezionare e collegare (mediante l'automazione) le esportazioni NFS Endurance in un intervallo di dimensioni che va da 20 GB a un massimo di 12 TB. {{site.data.keyword.cloud_notm}} consente a un massimo di 64 host vSphere ESXi di connettersi a una singola esportazione NFS Endurance.

Endurance è disponibile in tre livelli di prestazioni IOPS per supportare esigenze applicative diverse. Nota: dopo che ne è stato eseguito il provisioning, la condivisione NFS non può essere ridimensionata o riconfigurata per consentire più o meno IOPS.

Per le opzioni IOPS dettagliate, vedi la sezione _Impostazioni di archiviazione_ in [Ordinazione di istanze vCenter Server](../../vcenter/vc_orderinginstance.html).

Oltre ai livelli di archiviazione, l'archiviazione Endurance di {{site.data.keyword.cloud_notm}} supporta un'ampia selezione di esigenze applicative, comprese le istantanee e la replica e la crittografia dei dati inattivi nelle ubicazioni {{site.data.keyword.CloudDataCent_notm}}.

### Link correlati

* [Panoramica della soluzione](../solution/solution_overview.html)
