# nutanix_user

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
module "nutanix_user" {
  source = "./modules/nutanix/d/nutanix_user"

  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # project_reference - (optional) is a type of map of string
  project_reference = {}
  # user_id - (optional) is a type of string
  user_id = null
  # user_name - (optional) is a type of string
  user_name = null

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

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name" {
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
data "nutanix_user" "this" {
  owner_reference   = var.owner_reference
  project_reference = var.project_reference
  user_id           = var.user_id
  user_name         = var.user_name

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
output "access_control_policy_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_user.this.access_control_policy_reference_list
}

output "api_version" {
  description = "returns a string"
  value       = data.nutanix_user.this.api_version
}

output "directory_service_user" {
  description = "returns a list of object"
  value       = data.nutanix_user.this.directory_service_user
}

output "display_name" {
  description = "returns a string"
  value       = data.nutanix_user.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_user.this.id
}

output "identity_provider_user" {
  description = "returns a list of object"
  value       = data.nutanix_user.this.identity_provider_user
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_user.this.metadata
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_user.this.owner_reference
}

output "project_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_user.this.project_reference_list
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_user.this.state
}

output "user_type" {
  description = "returns a string"
  value       = data.nutanix_user.this.user_type
}

output "this" {
  value = nutanix_user.this
}
```

[top](#index)