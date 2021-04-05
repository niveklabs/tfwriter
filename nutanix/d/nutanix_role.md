# nutanix_role

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
module "nutanix_role" {
  source = "./modules/nutanix/d/nutanix_role"

  # role_id - (optional) is a type of string
  role_id = null
  # role_name - (optional) is a type of string
  role_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "role_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_name" {
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
data "nutanix_role" "this" {
  role_id   = var.role_id
  role_name = var.role_name

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
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
  value       = data.nutanix_role.this.api_version
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_role.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_role.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_role.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_role.this.name
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_role.this.owner_reference
}

output "permission_reference_list" {
  description = "returns a set of object"
  value       = data.nutanix_role.this.permission_reference_list
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_role.this.project_reference
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_role.this.state
}

output "this" {
  value = nutanix_role.this
}
```

[top](#index)