# nutanix_project

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
module "nutanix_project" {
  source = "./modules/nutanix/d/nutanix_project"

  # project_id - (optional) is a type of string
  project_id = null
  # project_name - (optional) is a type of string
  project_name = null

  categories = [{
    name  = null
    value = null
  }]

  external_user_group_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  subnet_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  user_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_name" {
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

variable "external_user_group_reference_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "subnet_reference_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "user_reference_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

### Datasource

```terraform
data "nutanix_project" "this" {
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # project_name - (optional) is a type of string
  project_name = var.project_name

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

  dynamic "external_user_group_reference_list" {
    for_each = var.external_user_group_reference_list
    content {
    }
  }

  dynamic "subnet_reference_list" {
    for_each = var.subnet_reference_list
    content {
    }
  }

  dynamic "user_reference_list" {
    for_each = var.user_reference_list
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_project.this.account_reference_list
}

output "api_version" {
  description = "returns a string"
  value       = data.nutanix_project.this.api_version
}

output "default_subnet_reference" {
  description = "returns a map of string"
  value       = data.nutanix_project.this.default_subnet_reference
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_project.this.description
}

output "environment_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_project.this.environment_reference_list
}

output "external_network_list" {
  description = "returns a list of object"
  value       = data.nutanix_project.this.external_network_list
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_project.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = data.nutanix_project.this.is_default
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_project.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_project.this.name
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_project.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_project.this.project_reference
}

output "resource_domain" {
  description = "returns a list of object"
  value       = data.nutanix_project.this.resource_domain
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_project.this.state
}

output "this" {
  value = nutanix_project.this
}
```

[top](#index)