---
layout: resource
title: signalfx
type: provider
resource: signalfx
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "signalfx" {
  version = "6.7.3"

  # api_url - (optional) is a type of string
  api_url = null
  # auth_token - (optional) is a type of string
  auth_token = null
  # custom_app_url - (optional) is a type of string
  custom_app_url = null
  # timeout_seconds - (optional) is a type of number
  timeout_seconds = null
}
```

[top](#index)

### Resources


- [signalfx_alert_muting_rule](./r/signalfx_alert_muting_rule.md)

- [signalfx_aws_external_integration](./r/signalfx_aws_external_integration.md)

- [signalfx_aws_integration](./r/signalfx_aws_integration.md)

- [signalfx_aws_token_integration](./r/signalfx_aws_token_integration.md)

- [signalfx_azure_integration](./r/signalfx_azure_integration.md)

- [signalfx_dashboard](./r/signalfx_dashboard.md)

- [signalfx_dashboard_group](./r/signalfx_dashboard_group.md)

- [signalfx_data_link](./r/signalfx_data_link.md)

- [signalfx_detector](./r/signalfx_detector.md)

- [signalfx_event_feed_chart](./r/signalfx_event_feed_chart.md)

- [signalfx_gcp_integration](./r/signalfx_gcp_integration.md)

- [signalfx_heatmap_chart](./r/signalfx_heatmap_chart.md)

- [signalfx_jira_integration](./r/signalfx_jira_integration.md)

- [signalfx_list_chart](./r/signalfx_list_chart.md)

- [signalfx_opsgenie_integration](./r/signalfx_opsgenie_integration.md)

- [signalfx_org_token](./r/signalfx_org_token.md)

- [signalfx_pagerduty_integration](./r/signalfx_pagerduty_integration.md)

- [signalfx_single_value_chart](./r/signalfx_single_value_chart.md)

- [signalfx_slack_integration](./r/signalfx_slack_integration.md)

- [signalfx_team](./r/signalfx_team.md)

- [signalfx_text_chart](./r/signalfx_text_chart.md)

- [signalfx_time_chart](./r/signalfx_time_chart.md)

- [signalfx_victor_ops_integration](./r/signalfx_victor_ops_integration.md)

- [signalfx_webhook_integration](./r/signalfx_webhook_integration.md)


[top](#index)

### Datasources


- [signalfx_aws_services](./d/signalfx_aws_services.md)

- [signalfx_azure_services](./d/signalfx_azure_services.md)

- [signalfx_dimension_values](./d/signalfx_dimension_values.md)

- [signalfx_gcp_services](./d/signalfx_gcp_services.md)

- [signalfx_pagerduty_integration](./d/signalfx_pagerduty_integration.md)


[top](#index)