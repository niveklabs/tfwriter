# nutanix_recovery_plan

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
module "nutanix_recovery_plan" {
  source = "./modules/nutanix/d/nutanix_recovery_plan"

  # recovery_plan_id - (optional) is a type of string
  recovery_plan_id = null
  # recovery_plan_name - (optional) is a type of string
  recovery_plan_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "recovery_plan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recovery_plan_name" {
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
data "nutanix_recovery_plan" "this" {
  # recovery_plan_id - (optional) is a type of string
  recovery_plan_id = var.recovery_plan_id
  # recovery_plan_name - (optional) is a type of string
  recovery_plan_name = var.recovery_plan_name

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
  value       = data.nutanix_recovery_plan.this.api_version
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_recovery_plan.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_recovery_plan.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_recovery_plan.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_recovery_plan.this.name
}

output "owner_reference" {
  description = "returns a list of object"
  value       = data.nutanix_recovery_plan.this.owner_reference
}

output "parameters" {
  description = "returns a list of object"
  value       = data.nutanix_recovery_plan.this.parameters
}

output "project_reference" {
  description = "returns a list of object"
  value       = data.nutanix_recovery_plan.this.project_reference
}

output "stage_list" {
  description = "returns a list of object"
  value       = data.nutanix_recovery_plan.this.stage_list
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_recovery_plan.this.state
}

output "this" {
  value = nutanix_recovery_plan.this
}
```

[top](#index)