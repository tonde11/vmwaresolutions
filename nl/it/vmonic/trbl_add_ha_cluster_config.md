---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-15"

---

# Problema di configurazione della console vSphere che si verifica all'aggiunta del cluster HA

## Problema
Quando aggiungi una configurazione cluster HA (alta disponibilità) con una sola condivisione file, viene visualizzato il seguente problema di configurazione sugli host ESXi:

`The number of heartbeat datastores for host is 1, which is less than required: 2`

## Risoluzione
Questo problema si verifica se non vi è ridondanza nell'archiviazione condivisa per consentire l'heartbeat dell'archivio dati.

Per ulteriori informazioni e i passi su come risolvere il problema, vedi [HA error: "The number of heartbeat datastores for host is 1, which is less than required: 2" (2004739)](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2004739).
