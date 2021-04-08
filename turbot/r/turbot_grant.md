# turbot_grant

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "turbot_grant" {
  source = "./modules/turbot/r/turbot_grant"

  # identity - (required) is a type of string
  identity = null
  # level - (required) is a type of string
  level = null
  # resource - (required) is a type of string
  resource = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "identity" {
  description = "(required)"
  type        = string
}

variable "level" {
  description = "(required)"
  type        = string
}

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

### Resource

```terraform
resource "turbot_grant" "this" {
  # identity - (required) is a type of string
  identity = var.identity
  # level - (required) is a type of string
  level = var.level
  # resource - (required) is a type of string
  resource = var.resource
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_grant.this.id
}

output "identity_akas" {
  description = "returns a list of string"
  value       = turbot_grant.this.identity_akas
}

output "permission_level_akas" {
  description = "returns a list of string"
  value       = turbot_grant.this.permission_level_akas
}

output "permission_type_akas" {
  description = "returns a list of string"
  value       = turbot_grant.this.permission_type_akas
}

output "resource_akas" {
  description = "returns a list of string"
  value       = turbot_grant.this.resource_akas
}

output "this" {
  value = turbot_grant.this
}
```

[top](#index)