---
layout: resource
title: circonus
type: provider
resource: circonus
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "circonus" {
  version = "0.12.0"

  # api_url - (optional) is a type of string
  api_url = null
  # auto_tag - (optional) is a type of bool
  auto_tag = null
  # key - (required) is a type of string
  key = null
}
```

[top](#index)

### Resources


- [circonus_check](./r/circonus_check.md)

- [circonus_contact_group](./r/circonus_contact_group.md)

- [circonus_dashboard](./r/circonus_dashboard.md)

- [circonus_graph](./r/circonus_graph.md)

- [circonus_maintenance](./r/circonus_maintenance.md)

- [circonus_metric](./r/circonus_metric.md)

- [circonus_overlay_set](./r/circonus_overlay_set.md)

- [circonus_rule_set](./r/circonus_rule_set.md)

- [circonus_rule_set_group](./r/circonus_rule_set_group.md)

- [circonus_worksheet](./r/circonus_worksheet.md)


[top](#index)

### Datasources


- [circonus_account](./d/circonus_account.md)

- [circonus_collector](./d/circonus_collector.md)


[top](#index)