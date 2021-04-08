# auth0_hook

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_hook" {
  source = "./modules/auth0/r/auth0_hook"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # script - (required) is a type of string
  script = null
  # trigger_id - (required) is a type of string
  trigger_id = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Whether the hook is enabled, or disabled"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of this hook"
  type        = string
}

variable "script" {
  description = "(required) - Code to be executed when this hook runs"
  type        = string
}

variable "trigger_id" {
  description = "(required) - Execution stage of this rule. Can be credentials-exchange, pre-user-registration, post-user-registration, post-change-password, or send-phone-message"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "auth0_hook" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # script - (required) is a type of string
  script = var.script
  # trigger_id - (required) is a type of string
  trigger_id = var.trigger_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_hook.this.id
}

output "this" {
  value = auth0_hook.this
}
```

[top](#index)