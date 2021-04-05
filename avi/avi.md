---
layout: resource
title: avi
type: provider
resource: avi
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "avi" {
  version = "0.2.3"

  # avi_api_timeout - (optional) is a type of number
  avi_api_timeout = null
  # avi_authtoken - (optional) is a type of string
  avi_authtoken = null
  # avi_controller - (optional) is a type of string
  avi_controller = null
  # avi_password - (optional) is a type of string
  avi_password = null
  # avi_tenant - (optional) is a type of string
  avi_tenant = null
  # avi_username - (optional) is a type of string
  avi_username = null
  # avi_version - (optional) is a type of string
  avi_version = null
}
```

[top](#index)

### Resources


- [avi_actiongroupconfig](./r/avi_actiongroupconfig.md)

- [avi_alertconfig](./r/avi_alertconfig.md)

- [avi_alertemailconfig](./r/avi_alertemailconfig.md)

- [avi_alertscriptconfig](./r/avi_alertscriptconfig.md)

- [avi_alertsyslogconfig](./r/avi_alertsyslogconfig.md)

- [avi_analyticsprofile](./r/avi_analyticsprofile.md)

- [avi_applicationpersistenceprofile](./r/avi_applicationpersistenceprofile.md)

- [avi_applicationprofile](./r/avi_applicationprofile.md)

- [avi_authprofile](./r/avi_authprofile.md)

- [avi_autoscalelaunchconfig](./r/avi_autoscalelaunchconfig.md)

- [avi_backup](./r/avi_backup.md)

- [avi_backupconfiguration](./r/avi_backupconfiguration.md)

- [avi_certificatemanagementprofile](./r/avi_certificatemanagementprofile.md)

- [avi_cloud](./r/avi_cloud.md)

- [avi_cloudconnectoruser](./r/avi_cloudconnectoruser.md)

- [avi_cloudproperties](./r/avi_cloudproperties.md)

- [avi_cluster](./r/avi_cluster.md)

- [avi_clusterclouddetails](./r/avi_clusterclouddetails.md)

- [avi_controllerportalregistration](./r/avi_controllerportalregistration.md)

- [avi_controllerproperties](./r/avi_controllerproperties.md)

- [avi_controllersite](./r/avi_controllersite.md)

- [avi_customerportalinfo](./r/avi_customerportalinfo.md)

- [avi_customipamdnsprofile](./r/avi_customipamdnsprofile.md)

- [avi_dnspolicy](./r/avi_dnspolicy.md)

- [avi_errorpagebody](./r/avi_errorpagebody.md)

- [avi_errorpageprofile](./r/avi_errorpageprofile.md)

- [avi_fileservice](./r/avi_fileservice.md)

- [avi_gslb](./r/avi_gslb.md)

- [avi_gslbgeodbprofile](./r/avi_gslbgeodbprofile.md)

- [avi_gslbservice](./r/avi_gslbservice.md)

- [avi_hardwaresecuritymodulegroup](./r/avi_hardwaresecuritymodulegroup.md)

- [avi_healthmonitor](./r/avi_healthmonitor.md)

- [avi_httppolicyset](./r/avi_httppolicyset.md)

- [avi_image](./r/avi_image.md)

- [avi_ipaddrgroup](./r/avi_ipaddrgroup.md)

- [avi_ipamdnsproviderprofile](./r/avi_ipamdnsproviderprofile.md)

- [avi_l4policyset](./r/avi_l4policyset.md)

- [avi_microservicegroup](./r/avi_microservicegroup.md)

- [avi_natpolicy](./r/avi_natpolicy.md)

- [avi_network](./r/avi_network.md)

- [avi_networkprofile](./r/avi_networkprofile.md)

- [avi_networksecuritypolicy](./r/avi_networksecuritypolicy.md)

- [avi_networkservice](./r/avi_networkservice.md)

- [avi_objectaccesspolicy](./r/avi_objectaccesspolicy.md)

- [avi_pingaccessagent](./r/avi_pingaccessagent.md)

- [avi_pkiprofile](./r/avi_pkiprofile.md)

- [avi_pool](./r/avi_pool.md)

- [avi_poolgroup](./r/avi_poolgroup.md)

- [avi_poolgroupdeploymentpolicy](./r/avi_poolgroupdeploymentpolicy.md)

- [avi_portalfileupload](./r/avi_portalfileupload.md)

- [avi_prioritylabels](./r/avi_prioritylabels.md)

- [avi_protocolparser](./r/avi_protocolparser.md)

- [avi_role](./r/avi_role.md)

- [avi_scheduler](./r/avi_scheduler.md)

- [avi_securitypolicy](./r/avi_securitypolicy.md)

- [avi_seproperties](./r/avi_seproperties.md)

- [avi_server](./r/avi_server.md)

- [avi_serverautoscalepolicy](./r/avi_serverautoscalepolicy.md)

- [avi_serviceengine](./r/avi_serviceengine.md)

- [avi_serviceenginegroup](./r/avi_serviceenginegroup.md)

- [avi_snmptrapprofile](./r/avi_snmptrapprofile.md)

- [avi_sslkeyandcertificate](./r/avi_sslkeyandcertificate.md)

- [avi_sslprofile](./r/avi_sslprofile.md)

- [avi_ssopolicy](./r/avi_ssopolicy.md)

- [avi_stringgroup](./r/avi_stringgroup.md)

- [avi_systemconfiguration](./r/avi_systemconfiguration.md)

- [avi_tenant](./r/avi_tenant.md)

- [avi_testsedatastorelevel1](./r/avi_testsedatastorelevel1.md)

- [avi_testsedatastorelevel2](./r/avi_testsedatastorelevel2.md)

- [avi_testsedatastorelevel3](./r/avi_testsedatastorelevel3.md)

- [avi_trafficcloneprofile](./r/avi_trafficcloneprofile.md)

- [avi_upgradestatusinfo](./r/avi_upgradestatusinfo.md)

- [avi_upgradestatussummary](./r/avi_upgradestatussummary.md)

- [avi_useraccount](./r/avi_useraccount.md)

- [avi_useraccountprofile](./r/avi_useraccountprofile.md)

- [avi_virtualservice](./r/avi_virtualservice.md)

- [avi_vrfcontext](./r/avi_vrfcontext.md)

- [avi_vsdatascriptset](./r/avi_vsdatascriptset.md)

- [avi_vsvip](./r/avi_vsvip.md)

- [avi_wafcrs](./r/avi_wafcrs.md)

- [avi_wafpolicy](./r/avi_wafpolicy.md)

- [avi_wafpolicypsmgroup](./r/avi_wafpolicypsmgroup.md)

- [avi_wafprofile](./r/avi_wafprofile.md)

- [avi_webhook](./r/avi_webhook.md)


[top](#index)

### Datasources


- [avi_actiongroupconfig](./d/avi_actiongroupconfig.md)

- [avi_alertconfig](./d/avi_alertconfig.md)

- [avi_alertemailconfig](./d/avi_alertemailconfig.md)

- [avi_alertscriptconfig](./d/avi_alertscriptconfig.md)

- [avi_alertsyslogconfig](./d/avi_alertsyslogconfig.md)

- [avi_analyticsprofile](./d/avi_analyticsprofile.md)

- [avi_applicationpersistenceprofile](./d/avi_applicationpersistenceprofile.md)

- [avi_applicationprofile](./d/avi_applicationprofile.md)

- [avi_authprofile](./d/avi_authprofile.md)

- [avi_autoscalelaunchconfig](./d/avi_autoscalelaunchconfig.md)

- [avi_backup](./d/avi_backup.md)

- [avi_backupconfiguration](./d/avi_backupconfiguration.md)

- [avi_certificatemanagementprofile](./d/avi_certificatemanagementprofile.md)

- [avi_cloud](./d/avi_cloud.md)

- [avi_cloudconnectoruser](./d/avi_cloudconnectoruser.md)

- [avi_cloudproperties](./d/avi_cloudproperties.md)

- [avi_cluster](./d/avi_cluster.md)

- [avi_clusterclouddetails](./d/avi_clusterclouddetails.md)

- [avi_controllerportalregistration](./d/avi_controllerportalregistration.md)

- [avi_controllerproperties](./d/avi_controllerproperties.md)

- [avi_controllersite](./d/avi_controllersite.md)

- [avi_customerportalinfo](./d/avi_customerportalinfo.md)

- [avi_customipamdnsprofile](./d/avi_customipamdnsprofile.md)

- [avi_dnspolicy](./d/avi_dnspolicy.md)

- [avi_errorpagebody](./d/avi_errorpagebody.md)

- [avi_errorpageprofile](./d/avi_errorpageprofile.md)

- [avi_fileservice](./d/avi_fileservice.md)

- [avi_gslb](./d/avi_gslb.md)

- [avi_gslbgeodbprofile](./d/avi_gslbgeodbprofile.md)

- [avi_gslbservice](./d/avi_gslbservice.md)

- [avi_hardwaresecuritymodulegroup](./d/avi_hardwaresecuritymodulegroup.md)

- [avi_healthmonitor](./d/avi_healthmonitor.md)

- [avi_httppolicyset](./d/avi_httppolicyset.md)

- [avi_image](./d/avi_image.md)

- [avi_ipaddrgroup](./d/avi_ipaddrgroup.md)

- [avi_ipamdnsproviderprofile](./d/avi_ipamdnsproviderprofile.md)

- [avi_l4policyset](./d/avi_l4policyset.md)

- [avi_microservicegroup](./d/avi_microservicegroup.md)

- [avi_natpolicy](./d/avi_natpolicy.md)

- [avi_network](./d/avi_network.md)

- [avi_networkprofile](./d/avi_networkprofile.md)

- [avi_networksecuritypolicy](./d/avi_networksecuritypolicy.md)

- [avi_networkservice](./d/avi_networkservice.md)

- [avi_objectaccesspolicy](./d/avi_objectaccesspolicy.md)

- [avi_pingaccessagent](./d/avi_pingaccessagent.md)

- [avi_pkiprofile](./d/avi_pkiprofile.md)

- [avi_pool](./d/avi_pool.md)

- [avi_poolgroup](./d/avi_poolgroup.md)

- [avi_poolgroupdeploymentpolicy](./d/avi_poolgroupdeploymentpolicy.md)

- [avi_portalfileupload](./d/avi_portalfileupload.md)

- [avi_prioritylabels](./d/avi_prioritylabels.md)

- [avi_protocolparser](./d/avi_protocolparser.md)

- [avi_role](./d/avi_role.md)

- [avi_scheduler](./d/avi_scheduler.md)

- [avi_securitypolicy](./d/avi_securitypolicy.md)

- [avi_seproperties](./d/avi_seproperties.md)

- [avi_server](./d/avi_server.md)

- [avi_serverautoscalepolicy](./d/avi_serverautoscalepolicy.md)

- [avi_serviceengine](./d/avi_serviceengine.md)

- [avi_serviceenginegroup](./d/avi_serviceenginegroup.md)

- [avi_snmptrapprofile](./d/avi_snmptrapprofile.md)

- [avi_sslkeyandcertificate](./d/avi_sslkeyandcertificate.md)

- [avi_sslprofile](./d/avi_sslprofile.md)

- [avi_ssopolicy](./d/avi_ssopolicy.md)

- [avi_stringgroup](./d/avi_stringgroup.md)

- [avi_systemconfiguration](./d/avi_systemconfiguration.md)

- [avi_tenant](./d/avi_tenant.md)

- [avi_testsedatastorelevel1](./d/avi_testsedatastorelevel1.md)

- [avi_testsedatastorelevel2](./d/avi_testsedatastorelevel2.md)

- [avi_testsedatastorelevel3](./d/avi_testsedatastorelevel3.md)

- [avi_trafficcloneprofile](./d/avi_trafficcloneprofile.md)

- [avi_upgradestatusinfo](./d/avi_upgradestatusinfo.md)

- [avi_upgradestatussummary](./d/avi_upgradestatussummary.md)

- [avi_useraccountprofile](./d/avi_useraccountprofile.md)

- [avi_virtualservice](./d/avi_virtualservice.md)

- [avi_vrfcontext](./d/avi_vrfcontext.md)

- [avi_vsdatascriptset](./d/avi_vsdatascriptset.md)

- [avi_vsvip](./d/avi_vsvip.md)

- [avi_wafcrs](./d/avi_wafcrs.md)

- [avi_wafpolicy](./d/avi_wafpolicy.md)

- [avi_wafpolicypsmgroup](./d/avi_wafpolicypsmgroup.md)

- [avi_wafprofile](./d/avi_wafprofile.md)

- [avi_webhook](./d/avi_webhook.md)


[top](#index)