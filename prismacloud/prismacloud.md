---
layout: resource
title: prismacloud
type: provider
resource: prismacloud
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "prismacloud" {
  version = "1.1.0"

  # customer_name - (optional) is a type of string
  customer_name = null
  # disable_reconnect - (optional) is a type of bool
  disable_reconnect = null
  # json_config_file - (optional) is a type of string
  json_config_file = null
  # json_web_token - (optional) is a type of string
  json_web_token = null
  # logging - (optional) is a type of map of bool
  logging = {}
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # skip_ssl_cert_verification - (optional) is a type of bool
  skip_ssl_cert_verification = null
  # timeout - (optional) is a type of number
  timeout = null
  # url - (optional) is a type of string
  url = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [prismacloud_account_group](./r/prismacloud_account_group.md)

- [prismacloud_alert_rule](./r/prismacloud_alert_rule.md)

- [prismacloud_cloud_account](./r/prismacloud_cloud_account.md)

- [prismacloud_compliance_standard](./r/prismacloud_compliance_standard.md)

- [prismacloud_compliance_standard_requirement](./r/prismacloud_compliance_standard_requirement.md)

- [prismacloud_compliance_standard_requirement_section](./r/prismacloud_compliance_standard_requirement_section.md)

- [prismacloud_enterprise_settings](./r/prismacloud_enterprise_settings.md)

- [prismacloud_integration](./r/prismacloud_integration.md)

- [prismacloud_policy](./r/prismacloud_policy.md)

- [prismacloud_rql_search](./r/prismacloud_rql_search.md)

- [prismacloud_saved_search](./r/prismacloud_saved_search.md)

- [prismacloud_user_role](./r/prismacloud_user_role.md)


[top](#index)

### Datasources


- [prismacloud_account_group](./d/prismacloud_account_group.md)

- [prismacloud_account_groups](./d/prismacloud_account_groups.md)

- [prismacloud_alert_rule](./d/prismacloud_alert_rule.md)

- [prismacloud_alert_rules](./d/prismacloud_alert_rules.md)

- [prismacloud_alerts](./d/prismacloud_alerts.md)

- [prismacloud_cloud_account](./d/prismacloud_cloud_account.md)

- [prismacloud_cloud_accounts](./d/prismacloud_cloud_accounts.md)

- [prismacloud_compliance_standard](./d/prismacloud_compliance_standard.md)

- [prismacloud_compliance_standard_requirement](./d/prismacloud_compliance_standard_requirement.md)

- [prismacloud_compliance_standard_requirement_section](./d/prismacloud_compliance_standard_requirement_section.md)

- [prismacloud_compliance_standard_requirement_sections](./d/prismacloud_compliance_standard_requirement_sections.md)

- [prismacloud_compliance_standard_requirements](./d/prismacloud_compliance_standard_requirements.md)

- [prismacloud_compliance_standards](./d/prismacloud_compliance_standards.md)

- [prismacloud_enterprise_settings](./d/prismacloud_enterprise_settings.md)

- [prismacloud_integration](./d/prismacloud_integration.md)

- [prismacloud_integrations](./d/prismacloud_integrations.md)

- [prismacloud_policies](./d/prismacloud_policies.md)

- [prismacloud_policy](./d/prismacloud_policy.md)

- [prismacloud_rql_historic_search](./d/prismacloud_rql_historic_search.md)

- [prismacloud_rql_historic_searches](./d/prismacloud_rql_historic_searches.md)


[top](#index)