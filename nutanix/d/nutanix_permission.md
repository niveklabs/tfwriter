# nutanix_permission

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
module "nutanix_permission" {
  source = "./modules/nutanix/d/nutanix_permission"

  # permission_id - (optional) is a type of string
  permission_id = null
  # permission_name - (optional) is a type of string
  permission_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "permission_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permission_name" {
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
data "nutanix_permission" "this" {
  # permission_id - (optional) is a type of string
  permission_id = var.permission_id
  # permission_name - (optional) is a type of string
  permission_name = var.permission_name

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
  value       = data.nutanix_permission.this.api_version
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_permission.this.description
}

output "fields" {
  description = "returns a list of object"
  value       = data.nutanix_permission.this.fields
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_permission.this.id
}

output "kind" {
  description = "returns a string"
  value       = data.nutanix_permission.this.kind
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_permission.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_permission.this.name
}

output "operation" {
  description = "returns a string"
  value       = data.nutanix_permission.this.operation
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_permission.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_permission.this.project_reference
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_permission.this.state
}

output "this" {
  value = nutanix_permission.this
}
```

[top](#index)