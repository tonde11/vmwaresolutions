---

copyright:

  years:  2016, 2018

lastupdated: "2018-07-20"

---

# Ordine, visualizzazione e rimozione dei servizi per le istanze vCenter Server with Hybridity Bundle

Puoi ordinare servizi per la tua istanza VMware vCenter Server on {{site.data.keyword.cloud}} with Hybridity Bundle, ad esempio una soluzione di ripristino di emergenza. Quando non hai più bisogno di questi servizi, puoi rimuoverli dalla tua istanza.

## Servizi disponibili per le istanze vCenter Server with Hybridity Bundle

Per le istanze vCenter Server with Hybridity Bundle sono disponibili i seguenti servizi.

Tabella 1. Servizi disponibili per le istanze vCenter Server with Hybridity Bundle

| Nome servizio | Disponibilità | Supporto istanza |
|----------------------------------------------------------------------------------------|------------------|
| [F5 on {{site.data.keyword.cloud_notm}}](../services/f5_considerations.html)                                 | Sì | V1.9 e successive |
| [FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](../services/fsa_considerations.html)       | Sì | V1.8 e successive |
| [FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](../services/fortinetvm_considerations.html) | Sì | V2.0 e successive |
| [HyTrust CloudControl on {{site.data.keyword.cloud_notm}}](../services/htcc_considerations.html)              | Sì | V2.3 e successive |
| [HyTrust DataControl on {{site.data.keyword.cloud_notm}}](../services/htdc_considerations.html)              | Sì | V2.3 e successive |
| [IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}}](../services/spp_considerations.html)         | Sì | V2.2 e successive |
| [KMIP for VMware on {{site.data.keyword.cloud_notm}}](../services/kmip_considerations.html)                  | Sì | V2.2 e successive |
| [Veeam on {{site.data.keyword.cloud_notm}}](../services/veeam_considerations.html)                           | Sì | V1.8 e successive |
| [VMware HCX on {{site.data.keyword.cloud_notm}}](../services/hcx_considerations.html)                        | Sì | V2.3 e successive |
| [Zerto on {{site.data.keyword.cloud_notm}}](../services/addingzertodr.html)                                  | Sì | V1.2 e successive |

## Aggiunta di servizi alle istanze vCenter Server with Hybridity Bundle

Per applicare un servizio alla tua istanza vCenter Server with Hybridity Bundle, fai clic sui link nella tabella per esaminare le considerazioni sul servizio, controlla i componenti distribuiti e segui le istruzioni negli argomenti relativi agli ordini per effettuare il tuo ordine.

### Risultati dell'installazione del servizio

Una volta completata correttamente l'installazione del servizio, riceverai una notifica via e-mail e il servizio verrà visualizzato nella scheda **Servizi** dei dettagli dell'istanza con lo stato **Installato**.

## Visualizzazione dei servizi per le istanze vCenter Server with Hybridity Bundle

1. Dalla console {{site.data.keyword.vmwaresolutions_short}}, fai clic su **Istanze distribuite** nel riquadro di navigazione a sinistra.
2. Nella tabella **Istanze vCenter Server**, fai clic sull'istanza per la quale vuoi visualizzare i servizi.
3. Fai clic su **Servizi** nel riquadro di navigazione a sinistra.
4. Nella pagina **Servizi**, fai clic su un servizio per esaminare le relative informazioni, come lo stato del servizio e altri dettagli.
5. A seconda del servizio visualizzato, puoi accedere alle relative console utilizzando le credenziali fornite nei dettagli del servizio e gestire quindi il servizio da qui.

## Rimozione dei servizi per le istanze vCenter Server with Hybridity Bundle

1. Dalla console {{site.data.keyword.vmwaresolutions_short}}, fai clic su **Istanze distribuite** nel riquadro di navigazione a sinistra.
2. Nella tabella **Istanze vCenter Server**, fai clic sull'istanza per la quale vuoi rimuovere i servizi.
3. Fai clic su **Servizi** nel riquadro di navigazione a sinistra.
4. Nella pagina **Servizi**, individua l'istanza del servizio che vuoi rimuovere e fai clic sull'icona **Elimina**.
5. Nella pagina **Elimina servizio**, esamina le eventuali considerazioni o avvertenze. Seleziona **Accetto** e fai clic su **Elimina**.

### Risultati della rimozione del servizio

Dopo che la tua richiesta di rimozione del servizio viene accettata, lo stato del servizio viene modificato in **In fase di rimozione**.

Una volta completata correttamente la rimozione del servizio, riceverai una notifica via e-mail e il servizio verrà rimosso dalla pagina **Servizi** dell'istanza.

**Attenzione**: per i servizi rimossi ti vengono addebitati costi fino alla fine del ciclo di fatturazione dell'infrastruttura {{site.data.keyword.cloud_notm}}.

### Link correlati

* [Domande frequenti](../vmonic/faq.html)
