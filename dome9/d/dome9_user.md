# dome9_user

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_user" {
  source = "./modules/dome9/d/dome9_user"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_user" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "access" {
  description = "returns a list of object"
  value       = data.dome9_user.this.access
}

output "can_switch_role" {
  description = "returns a bool"
  value       = data.dome9_user.this.can_switch_role
}

output "create" {
  description = "returns a list of string"
  value       = data.dome9_user.this.create
}

output "cross_account_access" {
  description = "returns a list of string"
  value       = data.dome9_user.this.cross_account_access
}

output "email" {
  description = "returns a string"
  value       = data.dome9_user.this.email
}

output "has_api_key" {
  description = "returns a bool"
  value       = data.dome9_user.this.has_api_key
}

output "has_api_key_v1" {
  description = "returns a bool"
  value       = data.dome9_user.this.has_api_key_v1
}

output "has_api_key_v2" {
  description = "returns a bool"
  value       = data.dome9_user.this.has_api_key_v2
}

output "iam_safe" {
  description = "returns a set of object"
  value       = data.dome9_user.this.iam_safe
}

output "id" {
  description = "returns a string"
  value       = data.dome9_user.this.id
}

output "is_auditor" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_auditor
}

output "is_locked" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_locked
}

output "is_mfa_enabled" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_mfa_enabled
}

output "is_mobile_device_paired" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_mobile_device_paired
}

output "is_owner" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_owner
}

output "is_sso_enabled" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_sso_enabled
}

output "is_super_user" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_super_user
}

output "is_suspended" {
  description = "returns a bool"
  value       = data.dome9_user.this.is_suspended
}

output "last_login" {
  description = "returns a string"
  value       = data.dome9_user.this.last_login
}

output "manage" {
  description = "returns a list of object"
  value       = data.dome9_user.this.manage
}

output "permit_alert_actions" {
  description = "returns a bool"
  value       = data.dome9_user.this.permit_alert_actions
}

output "permit_notifications" {
  description = "returns a bool"
  value       = data.dome9_user.this.permit_notifications
}

output "permit_on_boarding" {
  description = "returns a bool"
  value       = data.dome9_user.this.permit_on_boarding
}

output "permit_policies" {
  description = "returns a bool"
  value       = data.dome9_user.this.permit_policies
}

output "permit_rulesets" {
  description = "returns a bool"
  value       = data.dome9_user.this.permit_rulesets
}

output "role_ids" {
  description = "returns a list of number"
  value       = data.dome9_user.this.role_ids
}

output "view" {
  description = "returns a list of object"
  value       = data.dome9_user.this.view
}

output "this" {
  value = dome9_user.this
}
```

[top](#index)