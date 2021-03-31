# akamai_appsec_eval_rule_condition_exception

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
module "akamai_appsec_eval_rule_condition_exception" {
  source = "./modules/akamai/d/akamai_appsec_eval_rule_condition_exception"

  # config_id - (required) is a type of number
  config_id = null
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

### Datasource

```terraform
data "akamai_appsec_eval_rule_condition_exception" "this" {
  config_id          = var.config_id
  rule_id            = var.rule_id
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_eval_rule_condition_exception.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_eval_rule_condition_exception.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_eval_rule_condition_exception.this.output_text
}

output "this" {
  value = akamai_appsec_eval_rule_condition_exception.this
}
```

[top](#index)