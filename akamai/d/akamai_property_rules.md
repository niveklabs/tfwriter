# akamai_property_rules

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
module "akamai_property_rules" {
  source = "./modules/akamai/d/akamai_property_rules"

  # contract_id - (optional) is a type of string
  contract_id = null
  # group_id - (optional) is a type of string
  group_id = null
  # property_id - (required) is a type of string
  property_id = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "property_id" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional) - This is a computed value - provider will always use 'latest' version, providing own version number is not supported"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_property_rules" "this" {
  # contract_id - (optional) is a type of string
  contract_id = var.contract_id
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # property_id - (required) is a type of string
  property_id = var.property_id
  # version - (optional) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "contract_id" {
  description = "returns a string"
  value       = data.akamai_property_rules.this.contract_id
}

output "errors" {
  description = "returns a string"
  value       = data.akamai_property_rules.this.errors
}

output "group_id" {
  description = "returns a string"
  value       = data.akamai_property_rules.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.akamai_property_rules.this.id
}

output "rules" {
  description = "returns a string"
  value       = data.akamai_property_rules.this.rules
}

output "version" {
  description = "returns a number"
  value       = data.akamai_property_rules.this.version
}

output "this" {
  value = akamai_property_rules.this
}
```

[top](#index)