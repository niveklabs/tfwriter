# nutanix_role

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/nutanix/r/nutanix_role"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  categories = [{
    name  = null
    value = null
  }]

  owner_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  permission_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  project_reference = [{
    kind = null
    name = null
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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

variable "owner_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "permission_reference_list" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
}

variable "project_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_role" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

  dynamic "owner_reference" {
    for_each = var.owner_reference
    content {
      # kind - (optional) is a type of string
      kind = owner_reference.value["kind"]
      # name - (optional) is a type of string
      name = owner_reference.value["name"]
      # uuid - (optional) is a type of string
      uuid = owner_reference.value["uuid"]
    }
  }

  dynamic "permission_reference_list" {
    for_each = var.permission_reference_list
    content {
      # kind - (optional) is a type of string
      kind = permission_reference_list.value["kind"]
      # name - (optional) is a type of string
      name = permission_reference_list.value["name"]
      # uuid - (required) is a type of string
      uuid = permission_reference_list.value["uuid"]
    }
  }

  dynamic "project_reference" {
    for_each = var.project_reference
    content {
      # kind - (optional) is a type of string
      kind = project_reference.value["kind"]
      # name - (optional) is a type of string
      name = project_reference.value["name"]
      # uuid - (optional) is a type of string
      uuid = project_reference.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_role.this.api_version
}

output "description" {
  description = "returns a string"
  value       = nutanix_role.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_role.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_role.this.metadata
}

output "state" {
  description = "returns a string"
  value       = nutanix_role.this.state
}

output "this" {
  value = nutanix_role.this
}
```

[top](#index)