# nutanix_protection_rule

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_protection_rule" {
  source = "./modules/nutanix/d/nutanix_protection_rule"

  # protection_rule_id - (optional) is a type of string
  protection_rule_id = null
  # protection_rule_name - (optional) is a type of string
  protection_rule_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "protection_rule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protection_rule_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_protection_rule" "this" {
  # protection_rule_id - (optional) is a type of string
  protection_rule_id = var.protection_rule_id
  # protection_rule_name - (optional) is a type of string
  protection_rule_name = var.protection_rule_name

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_protection_rule.this.api_version
}

output "availability_zone_connectivity_list" {
  description = "returns a list of object"
  value       = data.nutanix_protection_rule.this.availability_zone_connectivity_list
}

output "category_filter" {
  description = "returns a list of object"
  value       = data.nutanix_protection_rule.this.category_filter
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_protection_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_protection_rule.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_protection_rule.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_protection_rule.this.name
}

output "ordered_availability_zone_list" {
  description = "returns a list of object"
  value       = data.nutanix_protection_rule.this.ordered_availability_zone_list
}

output "owner_reference" {
  description = "returns a list of object"
  value       = data.nutanix_protection_rule.this.owner_reference
}

output "project_reference" {
  description = "returns a list of object"
  value       = data.nutanix_protection_rule.this.project_reference
}

output "start_time" {
  description = "returns a string"
  value       = data.nutanix_protection_rule.this.start_time
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_protection_rule.this.state
}

output "this" {
  value = nutanix_protection_rule.this
}
```

[top](#index)