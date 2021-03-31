# datadog

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "datadog" {
  version = "2.24.0"

  # api_key - (optional) is a type of string
  api_key = null
  # api_url - (optional) is a type of string
  api_url = null
  # app_key - (optional) is a type of string
  app_key = null
  # validate - (optional) is a type of bool
  validate = null
}
```

[top](#index)

### Resources


- [datadog_dashboard](./r/datadog_dashboard.md)

- [datadog_dashboard_json](./r/datadog_dashboard_json.md)

- [datadog_dashboard_list](./r/datadog_dashboard_list.md)

- [datadog_downtime](./r/datadog_downtime.md)

- [datadog_integration_aws](./r/datadog_integration_aws.md)

- [datadog_integration_aws_lambda_arn](./r/datadog_integration_aws_lambda_arn.md)

- [datadog_integration_aws_log_collection](./r/datadog_integration_aws_log_collection.md)

- [datadog_integration_aws_tag_filter](./r/datadog_integration_aws_tag_filter.md)

- [datadog_integration_azure](./r/datadog_integration_azure.md)

- [datadog_integration_gcp](./r/datadog_integration_gcp.md)

- [datadog_integration_pagerduty](./r/datadog_integration_pagerduty.md)

- [datadog_integration_pagerduty_service_object](./r/datadog_integration_pagerduty_service_object.md)

- [datadog_integration_slack_channel](./r/datadog_integration_slack_channel.md)

- [datadog_logs_archive](./r/datadog_logs_archive.md)

- [datadog_logs_archive_order](./r/datadog_logs_archive_order.md)

- [datadog_logs_custom_pipeline](./r/datadog_logs_custom_pipeline.md)

- [datadog_logs_index](./r/datadog_logs_index.md)

- [datadog_logs_index_order](./r/datadog_logs_index_order.md)

- [datadog_logs_integration_pipeline](./r/datadog_logs_integration_pipeline.md)

- [datadog_logs_metric](./r/datadog_logs_metric.md)

- [datadog_logs_pipeline_order](./r/datadog_logs_pipeline_order.md)

- [datadog_metric_metadata](./r/datadog_metric_metadata.md)

- [datadog_metric_tag_configuration](./r/datadog_metric_tag_configuration.md)

- [datadog_monitor](./r/datadog_monitor.md)

- [datadog_role](./r/datadog_role.md)

- [datadog_screenboard](./r/datadog_screenboard.md)

- [datadog_security_monitoring_default_rule](./r/datadog_security_monitoring_default_rule.md)

- [datadog_security_monitoring_rule](./r/datadog_security_monitoring_rule.md)

- [datadog_service_level_objective](./r/datadog_service_level_objective.md)

- [datadog_slo_correction](./r/datadog_slo_correction.md)

- [datadog_synthetics_global_variable](./r/datadog_synthetics_global_variable.md)

- [datadog_synthetics_private_location](./r/datadog_synthetics_private_location.md)

- [datadog_synthetics_test](./r/datadog_synthetics_test.md)

- [datadog_timeboard](./r/datadog_timeboard.md)

- [datadog_user](./r/datadog_user.md)


[top](#index)

### Datasources


- [datadog_dashboard](./d/datadog_dashboard.md)

- [datadog_dashboard_list](./d/datadog_dashboard_list.md)

- [datadog_ip_ranges](./d/datadog_ip_ranges.md)

- [datadog_monitor](./d/datadog_monitor.md)

- [datadog_permissions](./d/datadog_permissions.md)

- [datadog_role](./d/datadog_role.md)

- [datadog_security_monitoring_rules](./d/datadog_security_monitoring_rules.md)

- [datadog_synthetics_locations](./d/datadog_synthetics_locations.md)


[top](#index)