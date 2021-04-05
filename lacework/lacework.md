---
layout: resource
title: lacework
type: provider
resource: lacework
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "lacework" {
  version = "0.3.1"

  # account - (optional) is a type of string
  account = null
  # api_key - (optional) is a type of string
  api_key = null
  # api_secret - (optional) is a type of string
  api_secret = null
  # profile - (optional) is a type of string
  profile = null
}
```

[top](#index)

### Resources


- [lacework_agent_access_token](./r/lacework_agent_access_token.md)

- [lacework_alert_channel_aws_cloudwatch](./r/lacework_alert_channel_aws_cloudwatch.md)

- [lacework_alert_channel_aws_s3](./r/lacework_alert_channel_aws_s3.md)

- [lacework_alert_channel_cisco_webex](./r/lacework_alert_channel_cisco_webex.md)

- [lacework_alert_channel_datadog](./r/lacework_alert_channel_datadog.md)

- [lacework_alert_channel_gcp_pub_sub](./r/lacework_alert_channel_gcp_pub_sub.md)

- [lacework_alert_channel_jira_cloud](./r/lacework_alert_channel_jira_cloud.md)

- [lacework_alert_channel_jira_server](./r/lacework_alert_channel_jira_server.md)

- [lacework_alert_channel_microsoft_teams](./r/lacework_alert_channel_microsoft_teams.md)

- [lacework_alert_channel_newrelic](./r/lacework_alert_channel_newrelic.md)

- [lacework_alert_channel_pagerduty](./r/lacework_alert_channel_pagerduty.md)

- [lacework_alert_channel_qradar](./r/lacework_alert_channel_qradar.md)

- [lacework_alert_channel_service_now](./r/lacework_alert_channel_service_now.md)

- [lacework_alert_channel_slack](./r/lacework_alert_channel_slack.md)

- [lacework_alert_channel_splunk](./r/lacework_alert_channel_splunk.md)

- [lacework_alert_channel_victorops](./r/lacework_alert_channel_victorops.md)

- [lacework_alert_channel_webhook](./r/lacework_alert_channel_webhook.md)

- [lacework_integration_aws_cfg](./r/lacework_integration_aws_cfg.md)

- [lacework_integration_aws_ct](./r/lacework_integration_aws_ct.md)

- [lacework_integration_azure_al](./r/lacework_integration_azure_al.md)

- [lacework_integration_azure_cfg](./r/lacework_integration_azure_cfg.md)

- [lacework_integration_docker_hub](./r/lacework_integration_docker_hub.md)

- [lacework_integration_docker_v2](./r/lacework_integration_docker_v2.md)

- [lacework_integration_ecr](./r/lacework_integration_ecr.md)

- [lacework_integration_gcp_at](./r/lacework_integration_gcp_at.md)

- [lacework_integration_gcp_cfg](./r/lacework_integration_gcp_cfg.md)

- [lacework_integration_gcr](./r/lacework_integration_gcr.md)


[top](#index)

### Datasources


- [lacework_agent_access_token](./d/lacework_agent_access_token.md)

- [lacework_api_token](./d/lacework_api_token.md)


[top](#index)