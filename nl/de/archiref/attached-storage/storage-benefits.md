---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-13"

---

# Informationen zum angehängten Speicher für vCenter Server

Beim angehängten Speicher handelt es sich um eine Erweiterung zum VMware vCenter Server on {{site.data.keyword.cloud}}-Angebot. In der Architektur der Lösung für den angehängten Speicher für VMware vCenter Server on {{site.data.keyword.cloud_notm}} werden die Komponenten der Lösung und die allgemeine Konfiguration aller Komponenten im Design beschrieben.

Weitere Informationen zum vCenter Server-Design finden Sie in der [Lösungsübersicht](../solution/solution_overview.html).

## Wichtigste Vorteile des angehängten Speichers für vCenter Server

Obwohl der angehängte Speicher keine Voraussetzung für VMware-Umgebungen darstellt, bietet sein Einsatz als gemeinsam genutzte Speichereinheit zahlreiche Vorteile für Benutzer im IT-Betrieb. Der Einsatz gemeinsam genutzter Speichereinheiten kann Sie bei der Erreichung einer hohen Verfügbarkeit, der Verwendung von Distributed Resource Scheduler (DRS), der effizienten Nutzung Ihrer Speicherkapazitäten und beim vereinfachten Management durch Aktivierung der vSphere-Funktionen unterstützen, die in der folgenden Tabelle beschrieben werden.

Tabelle 1. Funktionsbeschreibung für angehängten Speicher für vCenter Server

| Funktion | Beschreibung |
|:------- |:----------- |
| vSphere Distributed Resource Scheduler und Ressourcenpools | Diese Funktion ermöglicht Ihnen die Abstraktion und das flexible Management von Ressourcen mithilfe des Lastausgleichs und der Platzierung virtueller Maschinen (VMs). Ressourcenpools können in Hierarchien zusammengefasst und zur hierarchischen Partitionierung der verfügbaren CPU- und Speicherressourcen genutzt werden. |
| vSphere High Availability (HA) | Diese Funktion bietet durch das VM-Pooling Hochverfügbarkeit (HA; High Availability) für VMs und für Hosts, die in einem Cluster enthalten sind. Die Hosts im Cluster werden überwacht. Tritt ein Fehler auf, dann werden die VMs, die sich auf einem ausgefallenen Host befinden, auf einem Ausweichhost neu gestartet. |
| vSphere Datastore Clusters | Diese Funktion stellt eine Reihe von Datenspeichern zur Verfügung, die über gemeinsam genutzte Ressourcen und eine entsprechende Managementschnittstelle verfügen. |
| vSphere Fault Tolerance | Diese Funktion bietet kontinuierliche Verfügbarkeit für VMs durch die Beseitigung von Ausfallzeiten und Unterbrechungen auch im Falle eines kompletten Hostausfalls. |

### Zugehörige Links

* [Lösungsübersicht](../solution/solution_overview.html)
