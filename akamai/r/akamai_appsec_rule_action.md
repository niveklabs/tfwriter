# akamai_appsec_rule_action

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
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_rule_action" {
  source = "./modules/akamai/r/akamai_appsec_rule_action"

  # config_id - (required) is a type of number
  config_id = null
  # rule_action - (required) is a type of string
  rule_action = null
  # rule_id - (required) is a type of number
  rule_id = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
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

variable "rule_action" {
  description = "(required)"
  type        = string
}

variable "rule_id" {
  description = "(required)"
  type        = number
}

variable "security_policy_id" {
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
resource "akamai_appsec_rule_action" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # rule_action - (required) is a type of string
  rule_action = var.rule_action
  # rule_id - (required) is a type of number
  rule_id = var.rule_id
  # security_policy_id - (required) is a type of string
  security_policy_id = var.security_policy_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_rule_action.this.id
}

output "this" {
  value = akamai_appsec_rule_action.this
}
```

[top](#index)