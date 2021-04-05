---
layout: resource
title: sumologic
type: provider
resource: sumologic
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "sumologic" {
  version = "2.9.1"

  # access_id - (required) is a type of string
  access_id = null
  # access_key - (required) is a type of string
  access_key = null
  # base_url - (optional) is a type of string
  base_url = null
  # environment - (optional) is a type of string
  environment = null
}
```

[top](#index)

### Resources


- [sumologic_aws_inventory_source](./r/sumologic_aws_inventory_source.md)

- [sumologic_aws_xray_source](./r/sumologic_aws_xray_source.md)

- [sumologic_cloud_to_cloud_source](./r/sumologic_cloud_to_cloud_source.md)

- [sumologic_cloudfront_source](./r/sumologic_cloudfront_source.md)

- [sumologic_cloudsyslog_source](./r/sumologic_cloudsyslog_source.md)

- [sumologic_cloudtrail_source](./r/sumologic_cloudtrail_source.md)

- [sumologic_cloudwatch_source](./r/sumologic_cloudwatch_source.md)

- [sumologic_collector](./r/sumologic_collector.md)

- [sumologic_collector_ingest_budget_assignment](./r/sumologic_collector_ingest_budget_assignment.md)

- [sumologic_connection](./r/sumologic_connection.md)

- [sumologic_content](./r/sumologic_content.md)

- [sumologic_dashboard](./r/sumologic_dashboard.md)

- [sumologic_elb_source](./r/sumologic_elb_source.md)

- [sumologic_field](./r/sumologic_field.md)

- [sumologic_field_extraction_rule](./r/sumologic_field_extraction_rule.md)

- [sumologic_folder](./r/sumologic_folder.md)

- [sumologic_gcp_source](./r/sumologic_gcp_source.md)

- [sumologic_http_source](./r/sumologic_http_source.md)

- [sumologic_ingest_budget](./r/sumologic_ingest_budget.md)

- [sumologic_ingest_budget_v2](./r/sumologic_ingest_budget_v2.md)

- [sumologic_lookup_table](./r/sumologic_lookup_table.md)

- [sumologic_metadata_source](./r/sumologic_metadata_source.md)

- [sumologic_monitor](./r/sumologic_monitor.md)

- [sumologic_monitor_folder](./r/sumologic_monitor_folder.md)

- [sumologic_partition](./r/sumologic_partition.md)

- [sumologic_password_policy](./r/sumologic_password_policy.md)

- [sumologic_polling_source](./r/sumologic_polling_source.md)

- [sumologic_role](./r/sumologic_role.md)

- [sumologic_s3_audit_source](./r/sumologic_s3_audit_source.md)

- [sumologic_s3_source](./r/sumologic_s3_source.md)

- [sumologic_saml_configuration](./r/sumologic_saml_configuration.md)

- [sumologic_scheduled_view](./r/sumologic_scheduled_view.md)

- [sumologic_subdomain](./r/sumologic_subdomain.md)

- [sumologic_user](./r/sumologic_user.md)


[top](#index)

### Datasources


- [sumologic_caller_identity](./d/sumologic_caller_identity.md)

- [sumologic_collector](./d/sumologic_collector.md)

- [sumologic_http_source](./d/sumologic_http_source.md)

- [sumologic_my_user_id](./d/sumologic_my_user_id.md)

- [sumologic_personal_folder](./d/sumologic_personal_folder.md)

- [sumologic_role](./d/sumologic_role.md)


[top](#index)