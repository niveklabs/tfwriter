# akamai_appsec_custom_rule

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
module "akamai_appsec_custom_rule" {
  source = "./modules/akamai/r/akamai_appsec_custom_rule"

  # config_id - (required) is a type of number
  config_id = null
  # custom_rule - (required) is a type of string
  custom_rule = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "custom_rule" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_custom_rule" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # custom_rule - (required) is a type of string
  custom_rule = var.custom_rule
}
```

[top](#index)

### Outputs

```terraform
output "custom_rule_id" {
  description = "returns a number"
  value       = akamai_appsec_custom_rule.this.custom_rule_id
}

output "id" {
  description = "returns a string"
  value       = akamai_appsec_custom_rule.this.id
}

output "this" {
  value = akamai_appsec_custom_rule.this
}
```

[top](#index)