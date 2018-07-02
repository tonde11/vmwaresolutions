---

copyright:

  years:  2016, 2018

lastupdated: "2018-06-07"

---

# IBM Spectrum Protect Plus on IBM Cloud verwalten

## Auf die IBM Spectrum Protect Plus-Managementkonsole zugreifen

Zum Management des Service "IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud}}" müssen Sie auf die IBM Spectrum Protect Plus-Managementkonsole zugreifen, indem Sie die folgenden Schritte ausführen:
1. Verwenden Sie das virtuelle private Netz der {{site.data.keyword.cloud_notm}}-Infrastruktur oder einen Jump-Server, um den Zugriff auf die IP-Adresse der virtuellen Maschine von IBM Spectrum Protect Plus zuzulassen. Die IP-Adresse finden Sie auf der Seite mit den Details für den Service "IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}}" in der {{site.data.keyword.vmwaresolutions_short}}-Konsole.
2. Klicken Sie zum Zugriff auf die IBM Spectrum Protect Plus-Managementkonsole auf der Seite mit den Details für den Service "IBM Spectrum Protect Plus on {{site.data.keyword.cloud}}" auf **IBM Spectrum Protect Plus-Konsole anzeigen** und melden Sie sich dann mit den Berechtigungsnachweisen an, die auf derselben Servicedetailseite aufgeführt sind.

## Programmkorrekturen für IBM Spectrum Protect Plus on IBM Cloud anwenden

Für die Wartung des Service "IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}}" und seine Aktualisierung auf die jeweils aktuelle Version sind Sie selbst zuständig. Die erforderlichen Updates können Sie von der Seite [IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} Support](https://www.ibm.com/mysupport/s/topic/0TO50000000IQWtGAO/spectrum-protect-plus) herunterladen.

Weitere Informationen finden Sie in den folgenden Abschnitten:
* [Services für Cloud Foundation-Instanzen bestellen, anzeigen und entfernen](../sddc/sd_addingremovingservices.html)
* [Services für vCenter Server-Instanzen bestellen, anzeigen und entfernen](../vcenter/vc_addingremovingservices.html)

## Betriebssystem der virtuellen Maschine von IBM Spectrum Protect Plus aktualisieren

Um das Betriebssystem der virtuellen Maschine von IBM Spectrum Protect Plus zu aktualisieren, müssen Sie sich als **Rootbenutzer** anmelden. Das Kennwort des **Rootbenutzers** ist identisch mit dem Kennwort, das auf der Seite mit den Details für den Service "IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}}" zu finden ist.

## Managementkomponenten für Instanzen mit installiertem Service "IBM Spectrum Protect Plus on IBM Cloud" sichern und wiederherstellen

 **Hinweis**: Die folgenden Informationen gelten für IBM Spectrum Protect Plus-Installationen auf Instanzen, die in V2.3 oder höheren Releases bereitgestellt (oder für die Upgrades auf diese Releases durchgeführt) wurden. Für V2.2-Instanzen stellt dieser Service den Datenschutz nur für die Workload-VMs bereit.

Der Service "IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}}" ist mit einem Managementsicherungsjob vorkonfiguriert, der täglich automatisch ausgeführt wird, um die folgenden Managementkomponenten mit bis zu sieben Wiederherstellungspunkten zu sichern:
* VMware vCenter Server
* Platform Services Controller (PSC)
* IBM CloudDriver
* **Nur bei Cloud Foundation-Instanzen**: VMware SDDC Manager
* **Nur bei vCenter Server-Instanzen mit HA-AD/DNS**: HA-Paar von AD/DNS

Wenn Fehler in den Managementkomponenten auftreten, können Sie ein Ticket öffnen, indem Sie den [IBM Support kontaktieren](../vmonic/trbl_support.html) um anzufordern, dass die Managementkomponenten anhand einer vorherigen Sicherung wiederhergestellt werden.

## Zugehörige Links

* [Überblick zu IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}}](spp_considerations.html)
* [Vorgehensweise zum Erhöhen des vsnap-Speichers für IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} nach der Bereitstellung](https://developer.ibm.com/recipes/tutorials/how-to-increase-vsnap-storage-for-ibm-spectrum-protect-plus-on-ibm-cloud-post-deployment/)
* [IBM Spectrum Protect Plus documentation](https://www.ibm.com/support/knowledgecenter/en/SSNQFQ/landing/welcome_ssnqfq.html)