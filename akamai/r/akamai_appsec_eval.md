# akamai_appsec_eval

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
module "akamai_appsec_eval" {
  source = "./modules/akamai/r/akamai_appsec_eval"

  # config_id - (required) is a type of number
  config_id = null
  # eval_operation - (required) is a type of string
  eval_operation = null
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

variable "eval_operation" {
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
resource "akamai_appsec_eval" "this" {
  config_id          = var.config_id
  eval_operation     = var.eval_operation
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "current_ruleset" {
  description = "returns a string"
  value       = akamai_appsec_eval.this.current_ruleset
}

output "eval_status" {
  description = "returns a string"
  value       = akamai_appsec_eval.this.eval_status
}

output "evaluating_ruleset" {
  description = "returns a string"
  value       = akamai_appsec_eval.this.evaluating_ruleset
}

output "expiration_date" {
  description = "returns a string"
  value       = akamai_appsec_eval.this.expiration_date
}

output "id" {
  description = "returns a string"
  value       = akamai_appsec_eval.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_eval.this.output_text
}

output "this" {
  value = akamai_appsec_eval.this
}
```

[top](#index)