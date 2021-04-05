---
layout: resource
title: grafana
type: provider
resource: grafana
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "grafana" {
  version = "1.9.0"

  # auth - (required) is a type of string
  auth = null
  # ca_cert - (optional) is a type of string
  ca_cert = null
  # insecure_skip_verify - (optional) is a type of bool
  insecure_skip_verify = null
  # org_id - (optional) is a type of number
  org_id = null
  # tls_cert - (optional) is a type of string
  tls_cert = null
  # tls_key - (optional) is a type of string
  tls_key = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Resources


- [grafana_alert_notification](./r/grafana_alert_notification.md)

- [grafana_dashboard](./r/grafana_dashboard.md)

- [grafana_dashboard_permission](./r/grafana_dashboard_permission.md)

- [grafana_data_source](./r/grafana_data_source.md)

- [grafana_folder](./r/grafana_folder.md)

- [grafana_folder_permission](./r/grafana_folder_permission.md)

- [grafana_organization](./r/grafana_organization.md)

- [grafana_team](./r/grafana_team.md)

- [grafana_team_preferences](./r/grafana_team_preferences.md)

- [grafana_user](./r/grafana_user.md)


[top](#index)

### Datasources



[top](#index)