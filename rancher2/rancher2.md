---
layout: resource
title: rancher2
type: provider
resource: rancher2
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "rancher2" {
  version = "1.13.0"

  # access_key - (optional) is a type of string
  access_key = null
  # api_url - (optional) is a type of string
  api_url = null
  # bootstrap - (optional) is a type of bool
  bootstrap = null
  # ca_certs - (optional) is a type of string
  ca_certs = null
  # insecure - (optional) is a type of bool
  insecure = null
  # retries - (optional) is a type of number
  retries = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # token_key - (optional) is a type of string
  token_key = null
}
```

[top](#index)

### Resources


- [rancher2_app](./r/rancher2_app.md)

- [rancher2_app_v2](./r/rancher2_app_v2.md)

- [rancher2_auth_config_activedirectory](./r/rancher2_auth_config_activedirectory.md)

- [rancher2_auth_config_adfs](./r/rancher2_auth_config_adfs.md)

- [rancher2_auth_config_azuread](./r/rancher2_auth_config_azuread.md)

- [rancher2_auth_config_freeipa](./r/rancher2_auth_config_freeipa.md)

- [rancher2_auth_config_github](./r/rancher2_auth_config_github.md)

- [rancher2_auth_config_keycloak](./r/rancher2_auth_config_keycloak.md)

- [rancher2_auth_config_okta](./r/rancher2_auth_config_okta.md)

- [rancher2_auth_config_openldap](./r/rancher2_auth_config_openldap.md)

- [rancher2_auth_config_ping](./r/rancher2_auth_config_ping.md)

- [rancher2_bootstrap](./r/rancher2_bootstrap.md)

- [rancher2_catalog](./r/rancher2_catalog.md)

- [rancher2_catalog_v2](./r/rancher2_catalog_v2.md)

- [rancher2_certificate](./r/rancher2_certificate.md)

- [rancher2_cloud_credential](./r/rancher2_cloud_credential.md)

- [rancher2_cluster](./r/rancher2_cluster.md)

- [rancher2_cluster_alert_group](./r/rancher2_cluster_alert_group.md)

- [rancher2_cluster_alert_rule](./r/rancher2_cluster_alert_rule.md)

- [rancher2_cluster_driver](./r/rancher2_cluster_driver.md)

- [rancher2_cluster_logging](./r/rancher2_cluster_logging.md)

- [rancher2_cluster_role_template_binding](./r/rancher2_cluster_role_template_binding.md)

- [rancher2_cluster_sync](./r/rancher2_cluster_sync.md)

- [rancher2_cluster_template](./r/rancher2_cluster_template.md)

- [rancher2_etcd_backup](./r/rancher2_etcd_backup.md)

- [rancher2_feature](./r/rancher2_feature.md)

- [rancher2_global_dns](./r/rancher2_global_dns.md)

- [rancher2_global_dns_provider](./r/rancher2_global_dns_provider.md)

- [rancher2_global_role](./r/rancher2_global_role.md)

- [rancher2_global_role_binding](./r/rancher2_global_role_binding.md)

- [rancher2_multi_cluster_app](./r/rancher2_multi_cluster_app.md)

- [rancher2_namespace](./r/rancher2_namespace.md)

- [rancher2_node_driver](./r/rancher2_node_driver.md)

- [rancher2_node_pool](./r/rancher2_node_pool.md)

- [rancher2_node_template](./r/rancher2_node_template.md)

- [rancher2_notifier](./r/rancher2_notifier.md)

- [rancher2_pod_security_policy_template](./r/rancher2_pod_security_policy_template.md)

- [rancher2_project](./r/rancher2_project.md)

- [rancher2_project_alert_group](./r/rancher2_project_alert_group.md)

- [rancher2_project_alert_rule](./r/rancher2_project_alert_rule.md)

- [rancher2_project_logging](./r/rancher2_project_logging.md)

- [rancher2_project_role_template_binding](./r/rancher2_project_role_template_binding.md)

- [rancher2_registry](./r/rancher2_registry.md)

- [rancher2_role_template](./r/rancher2_role_template.md)

- [rancher2_secret](./r/rancher2_secret.md)

- [rancher2_secret_v2](./r/rancher2_secret_v2.md)

- [rancher2_setting](./r/rancher2_setting.md)

- [rancher2_token](./r/rancher2_token.md)

- [rancher2_user](./r/rancher2_user.md)


[top](#index)

### Datasources


- [rancher2_app](./d/rancher2_app.md)

- [rancher2_catalog](./d/rancher2_catalog.md)

- [rancher2_catalog_v2](./d/rancher2_catalog_v2.md)

- [rancher2_certificate](./d/rancher2_certificate.md)

- [rancher2_cloud_credential](./d/rancher2_cloud_credential.md)

- [rancher2_cluster](./d/rancher2_cluster.md)

- [rancher2_cluster_alert_group](./d/rancher2_cluster_alert_group.md)

- [rancher2_cluster_alert_rule](./d/rancher2_cluster_alert_rule.md)

- [rancher2_cluster_driver](./d/rancher2_cluster_driver.md)

- [rancher2_cluster_logging](./d/rancher2_cluster_logging.md)

- [rancher2_cluster_role_template_binding](./d/rancher2_cluster_role_template_binding.md)

- [rancher2_cluster_scan](./d/rancher2_cluster_scan.md)

- [rancher2_cluster_template](./d/rancher2_cluster_template.md)

- [rancher2_etcd_backup](./d/rancher2_etcd_backup.md)

- [rancher2_global_dns_provider](./d/rancher2_global_dns_provider.md)

- [rancher2_global_role](./d/rancher2_global_role.md)

- [rancher2_global_role_binding](./d/rancher2_global_role_binding.md)

- [rancher2_multi_cluster_app](./d/rancher2_multi_cluster_app.md)

- [rancher2_namespace](./d/rancher2_namespace.md)

- [rancher2_node_driver](./d/rancher2_node_driver.md)

- [rancher2_node_pool](./d/rancher2_node_pool.md)

- [rancher2_node_template](./d/rancher2_node_template.md)

- [rancher2_notifier](./d/rancher2_notifier.md)

- [rancher2_pod_security_policy_template](./d/rancher2_pod_security_policy_template.md)

- [rancher2_project](./d/rancher2_project.md)

- [rancher2_project_alert_group](./d/rancher2_project_alert_group.md)

- [rancher2_project_alert_rule](./d/rancher2_project_alert_rule.md)

- [rancher2_project_logging](./d/rancher2_project_logging.md)

- [rancher2_project_role_template_binding](./d/rancher2_project_role_template_binding.md)

- [rancher2_registry](./d/rancher2_registry.md)

- [rancher2_role_template](./d/rancher2_role_template.md)

- [rancher2_secret](./d/rancher2_secret.md)

- [rancher2_secret_v2](./d/rancher2_secret_v2.md)

- [rancher2_setting](./d/rancher2_setting.md)

- [rancher2_user](./d/rancher2_user.md)


[top](#index)