# akamai_appsec_custom_rules

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
module "akamai_appsec_custom_rules" {
  source = "./modules/akamai/d/akamai_appsec_custom_rules"

  # config_id - (required) is a type of number
  config_id = null
  # custom_rule_id - (optional) is a type of number
  custom_rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "custom_rule_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_custom_rules" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # custom_rule_id - (optional) is a type of number
  custom_rule_id = var.custom_rule_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_custom_rules.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_custom_rules.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_custom_rules.this.output_text
}

output "this" {
  value = akamai_appsec_custom_rules.this
}
```

[top](#index)