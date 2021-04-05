# prismacloud_enterprise_settings

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_enterprise_settings" {
  source = "./modules/prismacloud/d/prismacloud_enterprise_settings"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "prismacloud_enterprise_settings" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "anomaly_alert_disposition" {
  description = "returns a string"
  value       = data.prismacloud_enterprise_settings.this.anomaly_alert_disposition
}

output "anomaly_training_model_threshold" {
  description = "returns a string"
  value       = data.prismacloud_enterprise_settings.this.anomaly_training_model_threshold
}

output "apply_default_policies_enabled" {
  description = "returns a bool"
  value       = data.prismacloud_enterprise_settings.this.apply_default_policies_enabled
}

output "default_policies_enabled" {
  description = "returns a map of bool"
  value       = data.prismacloud_enterprise_settings.this.default_policies_enabled
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_enterprise_settings.this.id
}

output "require_alert_dismissal_note" {
  description = "returns a bool"
  value       = data.prismacloud_enterprise_settings.this.require_alert_dismissal_note
}

output "session_timeout" {
  description = "returns a number"
  value       = data.prismacloud_enterprise_settings.this.session_timeout
}

output "user_attribution_in_notification" {
  description = "returns a bool"
  value       = data.prismacloud_enterprise_settings.this.user_attribution_in_notification
}

output "this" {
  value = prismacloud_enterprise_settings.this
}
```

[top](#index)