# akamai_appsec_waf_mode

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
module "akamai_appsec_waf_mode" {
  source = "./modules/akamai/d/akamai_appsec_waf_mode"

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

### Datasource

```terraform
data "akamai_appsec_waf_mode" "this" {
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
  value       = data.akamai_appsec_waf_mode.this.current_ruleset
}

output "eval_expiration_date" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.eval_expiration_date
}

output "eval_ruleset" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.eval_ruleset
}

output "eval_status" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.eval_status
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.json
}

output "mode" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.mode
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_waf_mode.this.output_text
}

output "this" {
  value = akamai_appsec_waf_mode.this
}
```

[top](#index)