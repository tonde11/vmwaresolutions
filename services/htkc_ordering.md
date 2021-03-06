---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-26"

---

# Ordering HyTrust KeyControl on IBM Cloud

You can order the HyTrust KeyControl on {{site.data.keyword.cloud}} service while you order a new instance with an HA-pair of HyTrust KeyControl appliances included or by adding the HyTrust KeyControl appliances to your existing instance.

## Ordering HyTrust KeyControl on IBM Cloud for a new instance

You can order a new instance with HyTrust KeyControl on {{site.data.keyword.cloud_notm}} by using one of the following methods:
* From the {{site.data.keyword.vmwaresolutions_short}} console, when you order a new instance, select **HyTrust KeyControl on IBM Cloud** in the **Services** section.
* From the {{site.data.keyword.cloud_notm}} catalog, select **HyTrust KeyControl on IBM Cloud**, specify the service settings, and select **Add to New Instance**.

## Ordering HyTrust KeyControl on IBM Cloud for an existing instance

You can add the HyTrust KeyControl on {{site.data.keyword.cloud_notm}} service into an existing instance by using one the following methods:
* From the {{site.data.keyword.vmwaresolutions_short}} console, view the instance that you want to add the service for, click **Services** on the left navigation pane, and click **Add**.
* From the {{site.data.keyword.cloud_notm}} catalog, select **HyTrust KeyControl on IBM Cloud**, specify the service settings, and select **Add to Existing Instance**.

## HyTrust KeyControl on IBM Cloud service configuration

When you order the service, provide the following settings.

Specify whether you want to create a two-node Highly Available KeyControl cluster:
* If you select this option, two KeyControl nodes are deployed and a new active-active highly available cluster is created. This is the default option.
* If you do not select this option, two stand-alone KeyControl nodes are deployed with no cluster created. The stand-alone nodes can be manually clustered or added to existing KeyControl clusters after deployment.

### Related links

* [HyTrust KeyControl on {{site.data.keyword.cloud_notm}} overview](htkc_considerations.html)
* [Managing HyTrust KeyControl on {{site.data.keyword.cloud_notm}}](managinghtkc.html)
* [Ordering, viewing, and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering, viewing, and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)
* [Ordering, viewing, and removing services for vCenter Server with Hybridity Bundle instances](../vcenter/vc_hybrid_addingremovingservices.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
* [FAQ](../vmonic/faq.html)
* [HyTrust website](https://www.hytrust.com/)
