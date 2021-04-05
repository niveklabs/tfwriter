# prismacloud_policy

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
module "prismacloud_policy" {
  source = "./modules/prismacloud/d/prismacloud_policy"

  # name - (optional) is a type of string
  name = null
  # policy_id - (optional) is a type of string
  policy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Policy name"
  type        = string
  default     = null
}

variable "policy_id" {
  description = "(optional) - Policy ID"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_policy" "this" {
  name      = var.name
  policy_id = var.policy_id
}
```

[top](#index)

### Outputs

```terraform
output "cloud_type" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.cloud_type
}

output "compliance_metadata" {
  description = "returns a list of object"
  value       = data.prismacloud_policy.this.compliance_metadata
}

output "created_by" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = data.prismacloud_policy.this.created_on
}

output "deleted" {
  description = "returns a bool"
  value       = data.prismacloud_policy.this.deleted
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.prismacloud_policy.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.prismacloud_policy.this.labels
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = data.prismacloud_policy.this.last_modified_on
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.name
}

output "open_alerts_count" {
  description = "returns a number"
  value       = data.prismacloud_policy.this.open_alerts_count
}

output "overridden" {
  description = "returns a bool"
  value       = data.prismacloud_policy.this.overridden
}

output "owner" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.owner
}

output "policy_id" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.policy_id
}

output "policy_mode" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.policy_mode
}

output "policy_type" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.policy_type
}

output "recommendation" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.recommendation
}

output "remediable" {
  description = "returns a bool"
  value       = data.prismacloud_policy.this.remediable
}

output "remediation" {
  description = "returns a list of object"
  value       = data.prismacloud_policy.this.remediation
}

output "restrict_alert_dismissal" {
  description = "returns a bool"
  value       = data.prismacloud_policy.this.restrict_alert_dismissal
}

output "rule" {
  description = "returns a list of object"
  value       = data.prismacloud_policy.this.rule
}

output "rule_last_modified_on" {
  description = "returns a number"
  value       = data.prismacloud_policy.this.rule_last_modified_on
}

output "severity" {
  description = "returns a string"
  value       = data.prismacloud_policy.this.severity
}

output "system_default" {
  description = "returns a bool"
  value       = data.prismacloud_policy.this.system_default
}

output "this" {
  value = prismacloud_policy.this
}
```

[top](#index)