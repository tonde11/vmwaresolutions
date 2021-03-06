---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-24"

---

# Commande, affichage et retrait de services pour des instances vCenter Server with Hybridity Bundle

Vous pouvez commander des services pour vos instances VMware vCenter Server on {{site.data.keyword.cloud}} with Hybridity Bundle, par exemple, une solution de reprise après incident. Lorsque vous n'avez plus besoin de ces services, vous pouvez les supprimer de vos instances.

## Services disponibles pour les instances vCenter Server with Hybridity Bundle

Les services suivants sont disponibles pour les instances vCenter Server with Hybridity Bundle :

Tableau 1. Services disponibles pour les instances vCenter Server with Hybridity Bundle

| Nom de service | Version de service | Version d'instance |
|----------------------------------------------------------------------------------------|------------------|
| [F5 on {{site.data.keyword.cloud_notm}}](../services/f5_considerations.html)                                 | BIG-IP VE v13.1 | A partir de V1.9 |
| [FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](../services/fsa_considerations.html)       | Série 300 | A partir de V1.8 |
| [FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](../services/fortinetvm_considerations.html) | 5.6 | A partir de V2.0 |
| [HyTrust CloudControl on {{site.data.keyword.cloud_notm}}](../services/htcc_considerations.html)              | 5.4.0 | A partir de V2.3 |
| [HyTrust DataControl on {{site.data.keyword.cloud_notm}}](../services/htdc_considerations.html)              | 4.2.1 | A partir de V2.3 |
| [HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](../services/htkc_considerations.html)              | 4.2 | A partir de V2.5 |
| [IBM Spectrum Protect&trade; Plus on {{site.data.keyword.cloud_notm}}](../services/spp_considerations.html)  | 10.1.1 Patch 1 | A partir de V2.2 |
| [KMIP for VMware on {{site.data.keyword.cloud_notm}}](../services/kmip_considerations.html)                  |   | A partir de V2.2 |
| [Veeam on {{site.data.keyword.cloud_notm}}](../services/veeam_considerations.html)                           | 9.5u3 | A partir de V1.8 |
| [VMware HCX on {{site.data.keyword.cloud_notm}}](../services/hcx_considerations.html)                        | 3.5.1 Build 8774389 | A partir de V2.3 |
| [Zerto on {{site.data.keyword.cloud_notm}}](../services/addingzertodr.html)                                  | 5.5 u4 Patch 2 | A partir de V1.2 |

## Ajout de services à des instances vCenter Server with Hybridity Bundle

Afin d'appliquer un service à votre instance vCenter Server with Hybridity Bundle, cliquez sur les liens dans le tableau pour passer en revue les remarques relatives au service. Ensuite, vérifiez les composants qui sont déployés et suivez les instructions décrites dans les rubriques de commande pour passer votre commande. 

### Résultats de l'installation d'un service

Lorsque l'installation du service est terminée, vous êtes prévenu par un courrier électronique, et le service s'affiche sur l'onglet **Services** de la page des détails de l'instance avec le statut **Installé**.

## Affichage des services pour les instances vCenter Server with Hybridity Bundle

1. A partir de la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Instances déployées** dans le panneau de navigation de gauche.
2. Dans le tableau **Instances vCenter Server**, cliquez sur l'instance dont vous souhaitez afficher les services.
3. Cliquez sur **Services** dans le panneau de navigation de gauche.
4. Sur la page **Services**, cliquez sur un service pour passer en revue les informations le concernant, par exemple, le statut du service et d'autres détails.
5. Selon le service visualisé, vous pouvez accéder aux consoles de service à l'aide des données d'identification fournies sur la page des détails de service et vous pouvez gérer le service à partir de là.

## Retrait de services pour les instances vCenter Server with Hybridity Bundle

1. A partir de la console {{site.data.keyword.vmwaresolutions_short}}, cliquez sur **Instances déployées** dans le panneau de navigation de gauche.
2. Dans le tableau **Instances vCenter Server**, cliquez sur l'instance dont vous souhaitez retirer des services.
3. Cliquez sur **Services** dans le panneau de navigation de gauche.
4. Sur la page **Services**, localisez l'instance de service que vous souhaitez retirer et cliquez sur l'icône **Supprimer**.
5. Dans la fenêtre **Supprimer un service**, passez en revue, le cas échéant, les remarques ou avertissements. Sélectionnez **Je comprends** et cliquez sur **Supprimer**.

### Résultats du retrait d'un service

Une fois votre demande de retrait du service acceptée, le service prend le statut **Retrait en cours**.

Lorsque le retrait du service est terminé, vous êtes prévenu par un courrier électronique, et le service est retiré de la page **Services** de l'instance.

**Attention** : les services retirés vous sont facturés jusqu'à échéance du cycle de facturation de l'infrastructure {{site.data.keyword.cloud_notm}}.

### Liens connexes

* [Foire aux questions](../vmonic/faq.html)
