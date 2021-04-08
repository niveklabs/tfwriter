# turbot_policy_value

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_policy_value" {
  source = "./modules/turbot/d/turbot_policy_value"

  # resource - (required) is a type of string
  resource = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "resource" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "turbot_policy_value" "this" {
  # resource - (required) is a type of string
  resource = var.resource
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "details" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.details
}

output "id" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.id
}

output "precedence" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.precedence
}

output "reason" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.reason
}

output "setting_id" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.setting_id
}

output "state" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.state
}

output "value" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.value
}

output "value_source" {
  description = "returns a string"
  value       = data.turbot_policy_value.this.value_source
}

output "this" {
  value = turbot_policy_value.this
}
```

[top](#index)