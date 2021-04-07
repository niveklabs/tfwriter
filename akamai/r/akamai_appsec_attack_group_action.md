# akamai_appsec_attack_group_action

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
module "akamai_appsec_attack_group_action" {
  source = "./modules/akamai/r/akamai_appsec_attack_group_action"

  # attack_group - (required) is a type of string
  attack_group = null
  # attack_group_action - (required) is a type of string
  attack_group_action = null
  # config_id - (required) is a type of number
  config_id = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "attack_group" {
  description = "(required)"
  type        = string
}

variable "attack_group_action" {
  description = "(required)"
  type        = string
}

variable "config_id" {
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
resource "akamai_appsec_attack_group_action" "this" {
  # attack_group - (required) is a type of string
  attack_group = var.attack_group
  # attack_group_action - (required) is a type of string
  attack_group_action = var.attack_group_action
  # config_id - (required) is a type of number
  config_id = var.config_id
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
  value       = akamai_appsec_attack_group_action.this.id
}

output "this" {
  value = akamai_appsec_attack_group_action.this
}
```

[top](#index)