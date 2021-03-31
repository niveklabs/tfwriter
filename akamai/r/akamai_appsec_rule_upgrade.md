# akamai_appsec_rule_upgrade

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
module "akamai_appsec_rule_upgrade" {
  source = "./modules/akamai/r/akamai_appsec_rule_upgrade"

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
resource "akamai_appsec_rule_upgrade" "this" {
  config_id          = var.config_id
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "current_ruleset" {
  description = "returns a string"
  value       = akamai_appsec_rule_upgrade.this.current_ruleset
}

output "eval_status" {
  description = "returns a string"
  value       = akamai_appsec_rule_upgrade.this.eval_status
}

output "id" {
  description = "returns a string"
  value       = akamai_appsec_rule_upgrade.this.id
}

output "mode" {
  description = "returns a string"
  value       = akamai_appsec_rule_upgrade.this.mode
}

output "this" {
  value = akamai_appsec_rule_upgrade.this
}
```

[top](#index)