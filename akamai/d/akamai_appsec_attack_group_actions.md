# akamai_appsec_attack_group_actions

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "akamai_appsec_attack_group_actions" {
  source = "./modules/akamai/d/akamai_appsec_attack_group_actions"

  # attack_group - (optional) is a type of string
  attack_group = null
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
  description = "(optional)"
  type        = string
  default     = null
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

### Datasource

```terraform
data "akamai_appsec_attack_group_actions" "this" {
  attack_group       = var.attack_group
  config_id          = var.config_id
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.akamai_appsec_attack_group_actions.this.action
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_attack_group_actions.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_attack_group_actions.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_attack_group_actions.this.output_text
}

output "this" {
  value = akamai_appsec_attack_group_actions.this
}
```

[top](#index)