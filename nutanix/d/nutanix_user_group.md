# nutanix_user_group

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
module "nutanix_user_group" {
  source = "./modules/nutanix/d/nutanix_user_group"

  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # project_reference - (optional) is a type of map of string
  project_reference = {}
  # user_group_distinguished_name - (optional) is a type of string
  user_group_distinguished_name = null
  # user_group_id - (optional) is a type of string
  user_group_id = null
  # user_group_name - (optional) is a type of string
  user_group_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "owner_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_group_distinguished_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_group_name" {
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
data "nutanix_user_group" "this" {
  # owner_reference - (optional) is a type of map of string
  owner_reference = var.owner_reference
  # project_reference - (optional) is a type of map of string
  project_reference = var.project_reference
  # user_group_distinguished_name - (optional) is a type of string
  user_group_distinguished_name = var.user_group_distinguished_name
  # user_group_id - (optional) is a type of string
  user_group_id = var.user_group_id
  # user_group_name - (optional) is a type of string
  user_group_name = var.user_group_name

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
output "access_control_policy_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_user_group.this.access_control_policy_reference_list
}

output "api_version" {
  description = "returns a string"
  value       = data.nutanix_user_group.this.api_version
}

output "directory_service_user_group" {
  description = "returns a list of object"
  value       = data.nutanix_user_group.this.directory_service_user_group
}

output "display_name" {
  description = "returns a string"
  value       = data.nutanix_user_group.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_user_group.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_user_group.this.metadata
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_user_group.this.owner_reference
}

output "project_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_user_group.this.project_reference_list
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_user_group.this.state
}

output "user_group_type" {
  description = "returns a string"
  value       = data.nutanix_user_group.this.user_group_type
}

output "this" {
  value = nutanix_user_group.this
}
```

[top](#index)