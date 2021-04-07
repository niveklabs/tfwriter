---
layout: resource
title: pagerduty
type: provider
resource: pagerduty
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "pagerduty" {
  version = "1.9.6"

  # skip_credentials_validation - (optional) is a type of bool
  skip_credentials_validation = null
  # token - (required) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [pagerduty_addon](./r/pagerduty_addon.md)

- [pagerduty_business_service](./r/pagerduty_business_service.md)

- [pagerduty_escalation_policy](./r/pagerduty_escalation_policy.md)

- [pagerduty_event_rule](./r/pagerduty_event_rule.md)

- [pagerduty_extension](./r/pagerduty_extension.md)

- [pagerduty_maintenance_window](./r/pagerduty_maintenance_window.md)

- [pagerduty_response_play](./r/pagerduty_response_play.md)

- [pagerduty_ruleset](./r/pagerduty_ruleset.md)

- [pagerduty_ruleset_rule](./r/pagerduty_ruleset_rule.md)

- [pagerduty_schedule](./r/pagerduty_schedule.md)

- [pagerduty_service](./r/pagerduty_service.md)

- [pagerduty_service_dependency](./r/pagerduty_service_dependency.md)

- [pagerduty_service_event_rule](./r/pagerduty_service_event_rule.md)

- [pagerduty_service_integration](./r/pagerduty_service_integration.md)

- [pagerduty_team](./r/pagerduty_team.md)

- [pagerduty_team_membership](./r/pagerduty_team_membership.md)

- [pagerduty_user](./r/pagerduty_user.md)

- [pagerduty_user_contact_method](./r/pagerduty_user_contact_method.md)

- [pagerduty_user_notification_rule](./r/pagerduty_user_notification_rule.md)


[top](#index)

### Datasources


- [pagerduty_business_service](./d/pagerduty_business_service.md)

- [pagerduty_escalation_policy](./d/pagerduty_escalation_policy.md)

- [pagerduty_extension_schema](./d/pagerduty_extension_schema.md)

- [pagerduty_priority](./d/pagerduty_priority.md)

- [pagerduty_ruleset](./d/pagerduty_ruleset.md)

- [pagerduty_schedule](./d/pagerduty_schedule.md)

- [pagerduty_service](./d/pagerduty_service.md)

- [pagerduty_team](./d/pagerduty_team.md)

- [pagerduty_user](./d/pagerduty_user.md)

- [pagerduty_user_contact_method](./d/pagerduty_user_contact_method.md)

- [pagerduty_vendor](./d/pagerduty_vendor.md)


[top](#index)