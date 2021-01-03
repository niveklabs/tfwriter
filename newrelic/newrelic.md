# newrelic

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "newrelic" {
  version = "2.14.0"

  # account_id - (required) is a type of number
  account_id = null
  # admin_api_key - (optional) is a type of string
  admin_api_key = null
  # api_key - (optional) is a type of string
  api_key = null
  # api_url - (optional) is a type of string
  api_url = null
  # cacert_file - (optional) is a type of string
  cacert_file = null
  # infrastructure_api_url - (optional) is a type of string
  infrastructure_api_url = null
  # insecure_skip_verify - (optional) is a type of bool
  insecure_skip_verify = null
  # insights_insert_key - (optional) is a type of string
  insights_insert_key = null
  # insights_insert_url - (optional) is a type of string
  insights_insert_url = null
  # insights_query_url - (optional) is a type of string
  insights_query_url = null
  # nerdgraph_api_url - (optional) is a type of string
  nerdgraph_api_url = null
  # region - (optional) is a type of string
  region = null
  # synthetics_api_url - (optional) is a type of string
  synthetics_api_url = null
}
```

[top](#index)

### Resources


- [newrelic_alert_channel](./r/newrelic_alert_channel.md)

- [newrelic_alert_condition](./r/newrelic_alert_condition.md)

- [newrelic_alert_muting_rule](./r/newrelic_alert_muting_rule.md)

- [newrelic_alert_policy](./r/newrelic_alert_policy.md)

- [newrelic_alert_policy_channel](./r/newrelic_alert_policy_channel.md)

- [newrelic_api_access_key](./r/newrelic_api_access_key.md)

- [newrelic_application_settings](./r/newrelic_application_settings.md)

- [newrelic_dashboard](./r/newrelic_dashboard.md)

- [newrelic_entity_tags](./r/newrelic_entity_tags.md)

- [newrelic_events_to_metrics_rule](./r/newrelic_events_to_metrics_rule.md)

- [newrelic_infra_alert_condition](./r/newrelic_infra_alert_condition.md)

- [newrelic_insights_event](./r/newrelic_insights_event.md)

- [newrelic_nrql_alert_condition](./r/newrelic_nrql_alert_condition.md)

- [newrelic_plugins_alert_condition](./r/newrelic_plugins_alert_condition.md)

- [newrelic_synthetics_alert_condition](./r/newrelic_synthetics_alert_condition.md)

- [newrelic_synthetics_monitor](./r/newrelic_synthetics_monitor.md)

- [newrelic_synthetics_monitor_script](./r/newrelic_synthetics_monitor_script.md)

- [newrelic_synthetics_multilocation_alert_condition](./r/newrelic_synthetics_multilocation_alert_condition.md)

- [newrelic_synthetics_secure_credential](./r/newrelic_synthetics_secure_credential.md)

- [newrelic_workload](./r/newrelic_workload.md)


[top](#index)

### Datasources


- [newrelic_account](./d/newrelic_account.md)

- [newrelic_alert_channel](./d/newrelic_alert_channel.md)

- [newrelic_alert_policy](./d/newrelic_alert_policy.md)

- [newrelic_application](./d/newrelic_application.md)

- [newrelic_entity](./d/newrelic_entity.md)

- [newrelic_key_transaction](./d/newrelic_key_transaction.md)

- [newrelic_plugin](./d/newrelic_plugin.md)

- [newrelic_plugin_component](./d/newrelic_plugin_component.md)

- [newrelic_synthetics_monitor](./d/newrelic_synthetics_monitor.md)

- [newrelic_synthetics_monitor_location](./d/newrelic_synthetics_monitor_location.md)

- [newrelic_synthetics_secure_credential](./d/newrelic_synthetics_secure_credential.md)


[top](#index)