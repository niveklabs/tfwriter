# akamai_appsec_waf_mode

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
module "akamai_appsec_waf_mode" {
  source = "./modules/akamai/r/akamai_appsec_waf_mode"

  # config_id - (required) is a type of number
  config_id = null
  # mode - (required) is a type of string
  mode = null
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

variable "mode" {
  description = "(required)"
  type        = string
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
resource "akamai_appsec_waf_mode" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # mode - (required) is a type of string
  mode = var.mode
  # security_policy_id - (required) is a type of string
  security_policy_id = var.security_policy_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "current_ruleset" {
  description = "returns a string"
  value       = akamai_appsec_waf_mode.this.current_ruleset
}

output "eval_expiration_date" {
  description = "returns a string"
  value       = akamai_appsec_waf_mode.this.eval_expiration_date
}

output "eval_ruleset" {
  description = "returns a string"
  value       = akamai_appsec_waf_mode.this.eval_ruleset
}

output "eval_status" {
  description = "returns a string"
  value       = akamai_appsec_waf_mode.this.eval_status
}

output "id" {
  description = "returns a string"
  value       = akamai_appsec_waf_mode.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_waf_mode.this.output_text
}

output "this" {
  value = akamai_appsec_waf_mode.this
}
```

[top](#index)