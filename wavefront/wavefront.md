---
layout: resource
title: wavefront
type: provider
resource: wavefront
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "wavefront" {
  version = "2.8.3"

  # address - (optional) is a type of string
  address = null
  # http_proxy - (optional) is a type of string
  http_proxy = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [wavefront_alert](./r/wavefront_alert.md)

- [wavefront_alert_target](./r/wavefront_alert_target.md)

- [wavefront_cloud_integration_app_dynamics](./r/wavefront_cloud_integration_app_dynamics.md)

- [wavefront_cloud_integration_aws_external_id](./r/wavefront_cloud_integration_aws_external_id.md)

- [wavefront_cloud_integration_azure](./r/wavefront_cloud_integration_azure.md)

- [wavefront_cloud_integration_azure_activity_log](./r/wavefront_cloud_integration_azure_activity_log.md)

- [wavefront_cloud_integration_cloudtrail](./r/wavefront_cloud_integration_cloudtrail.md)

- [wavefront_cloud_integration_cloudwatch](./r/wavefront_cloud_integration_cloudwatch.md)

- [wavefront_cloud_integration_ec2](./r/wavefront_cloud_integration_ec2.md)

- [wavefront_cloud_integration_gcp](./r/wavefront_cloud_integration_gcp.md)

- [wavefront_cloud_integration_gcp_billing](./r/wavefront_cloud_integration_gcp_billing.md)

- [wavefront_cloud_integration_newrelic](./r/wavefront_cloud_integration_newrelic.md)

- [wavefront_cloud_integration_tesla](./r/wavefront_cloud_integration_tesla.md)

- [wavefront_dashboard](./r/wavefront_dashboard.md)

- [wavefront_dashboard_json](./r/wavefront_dashboard_json.md)

- [wavefront_derived_metric](./r/wavefront_derived_metric.md)

- [wavefront_external_link](./r/wavefront_external_link.md)

- [wavefront_ingestion_policy](./r/wavefront_ingestion_policy.md)

- [wavefront_maintenance_window](./r/wavefront_maintenance_window.md)

- [wavefront_role](./r/wavefront_role.md)

- [wavefront_service_account](./r/wavefront_service_account.md)

- [wavefront_user](./r/wavefront_user.md)

- [wavefront_user_group](./r/wavefront_user_group.md)


[top](#index)

### Datasources


- [wavefront_default_user_group](./d/wavefront_default_user_group.md)


[top](#index)