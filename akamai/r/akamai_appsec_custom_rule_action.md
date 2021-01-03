# akamai_appsec_custom_rule_action

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_custom_rule_action" {
  source = "./modules/akamai/r/akamai_appsec_custom_rule_action"

  # config_id - (required) is a type of number
  config_id = null
  # custom_rule_action - (required) is a type of string
  custom_rule_action = null
  # custom_rule_id - (required) is a type of number
  custom_rule_id = null
  # policy_id - (required) is a type of string
  policy_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "custom_rule_action" {
  description = "(required)"
  type        = string
}

variable "custom_rule_id" {
  description = "(required)"
  type        = number
}

variable "policy_id" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_custom_rule_action" "this" {
  config_id          = var.config_id
  custom_rule_action = var.custom_rule_action
  custom_rule_id     = var.custom_rule_id
  policy_id          = var.policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_custom_rule_action.this.id
}

output "this" {
  value = akamai_appsec_custom_rule_action.this
}
```

[top](#index)