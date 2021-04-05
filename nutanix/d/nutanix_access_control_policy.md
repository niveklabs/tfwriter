# nutanix_access_control_policy

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
module "nutanix_access_control_policy" {
  source = "./modules/nutanix/d/nutanix_access_control_policy"

  # access_control_policy_id - (optional) is a type of string
  access_control_policy_id = null
  # access_control_policy_name - (optional) is a type of string
  access_control_policy_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_control_policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_control_policy_name" {
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
data "nutanix_access_control_policy" "this" {
  access_control_policy_id   = var.access_control_policy_id
  access_control_policy_name = var.access_control_policy_name

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
  value       = data.nutanix_access_control_policy.this.api_version
}

output "context_filter_list" {
  description = "returns a list of object"
  value       = data.nutanix_access_control_policy.this.context_filter_list
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_access_control_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_access_control_policy.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_access_control_policy.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_access_control_policy.this.name
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_access_control_policy.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_access_control_policy.this.project_reference
}

output "role_reference" {
  description = "returns a list of object"
  value       = data.nutanix_access_control_policy.this.role_reference
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_access_control_policy.this.state
}

output "user_group_reference_list" {
  description = "returns a set of object"
  value       = data.nutanix_access_control_policy.this.user_group_reference_list
}

output "user_reference_list" {
  description = "returns a set of object"
  value       = data.nutanix_access_control_policy.this.user_reference_list
}

output "this" {
  value = nutanix_access_control_policy.this
}
```

[top](#index)