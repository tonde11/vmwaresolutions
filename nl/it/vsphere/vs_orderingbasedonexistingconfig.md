---

copyright:

  years:  2016, 2018

lastupdated: "2018-08-10"

---

# Ordine di cluster vSphere in base alle configurazioni esistenti

Puoi ordinare un cluster VMware vSphere in base a un template di configurazione che hai salvato. Utilizza questa procedura per definire la configurazione di un nuovo cluster basata su una configurazione cluster esistente.

## Requisiti

Assicurati di aver completato le seguenti attività:
*  Hai configurato le credenziali dell'infrastruttura {{site.data.keyword.cloud}} nella pagina **Impostazioni**. Per ulteriori informazioni, vedi [Account utente e impostazioni](../vmonic/useraccount.html).
*  Hai esaminato i requisiti e le considerazioni in [Requisiti e pianificazione per i cluster vSphere](vs_planning.html).
*  Hai creato un template di configurazione da riutilizzare.

## Procedura

1. Dal catalogo {{site.data.keyword.cloud_notm}}, fai clic su **VMware** nel riquadro di navigazione a sinistra e poi su **VMware vSphere** nella sezione **Data center virtuali**.
2. Nella pagina **VMware vSphere on IBM Cloud**, fai clic su **Crea**.  
3. Fai clic sulla scheda **Crea nuovo** e seleziona un template di configurazione dell'elenco **Configurazioni cluster**.
4. Immetti il nome del nuovo cluster.
5. Esamina le impostazioni del cluster che vengono completate automaticamente e aggiorna le impostazioni in base alle tue esigenze. Per ulteriori informazioni sulle impostazioni, vedi [Ordine di nuovi cluster vSphere](vs_orderinginstances.html).
6. Nel riquadro **Riepilogo ordine**, verifica la configurazione dell'istanza e il costo stimato.
   * Per salvare la configurazione come template senza effettuare un ordine, fai clic su **Salva configurazione**.
   * Per effettuare l'ordine, assicurati che l'account da addebitare sia corretto, esamina e accetta i termini e infine fai clic su **Fornitura**.

   **Nota**: vengono installati solo i {{site.data.keyword.baremetal_short}}. Sei responsabile dell'installazione e della configurazione dei vari componenti dopo la distribuzione del cluster, come VMware vCenter, VMware NSX, VMware vSAN.

## Risultati

Se hai salvato la configurazione del cluster come template, ricevi una notifica dalla console che indica che la configurazione è stata salvata. Potrai quindi trovare il template nell'elenco **Configurazioni cluster**.

Se hai effettuato un ordine, la distribuzione del cluster inizia automaticamente. Riceverai un'e-mail di conferma che ti indica che l'ordine è in fase di elaborazione. Quando il cluster è pronto per l'uso, ti viene inviata un'altra notifica e-mail.

**Nota:** i cluster vSphere, a differenza delle istanze vCenter Server e Cloud Foundation, non vengono visualizzati nella pagina **Istanze distribuite**.

### Link correlati

* [Ordine di nuovi cluster vSphere](vs_orderinginstances.html)
* [Ridimensionamento di cluster vSphere esistenti](vs_scalingexistingclusters.html)
* [Ridimensionamento di cluster creati all'esterno della console](vs_orderingforclustersoutside.html)
