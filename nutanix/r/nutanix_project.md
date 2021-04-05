# nutanix_project

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
module "nutanix_project" {
  source = "./modules/nutanix/r/nutanix_project"

  # api_version - (optional) is a type of string
  api_version = null
  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # project_reference - (optional) is a type of map of string
  project_reference = {}

  account_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  categories = [{
    name  = null
    value = null
  }]

  default_subnet_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  environment_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  external_network_list = [{
    name = null
    uuid = null
  }]

  external_user_group_reference_list = [{
    kind = null
    name = null
    uuid = null
  }]

  resource_domain = [{
    resources = [{
      limit         = null
      resource_type = null
      units         = null
      value         = null
    }]
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
variable "api_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

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

variable "account_reference_list" {
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

variable "default_subnet_reference" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
}

variable "environment_reference_list" {
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

variable "external_network_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "external_user_group_reference_list" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "resource_domain" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      resources = list(object(
        {
          limit         = number
          resource_type = string
          units         = string
          value         = number
        }
      ))
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
  description = "nested block: NestingSet, min items: 0, max items: 0"
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
resource "nutanix_project" "this" {
  api_version       = var.api_version
  description       = var.description
  name              = var.name
  owner_reference   = var.owner_reference
  project_reference = var.project_reference

  dynamic "account_reference_list" {
    for_each = var.account_reference_list
    content {
      kind = account_reference_list.value["kind"]
      name = account_reference_list.value["name"]
      uuid = account_reference_list.value["uuid"]
    }
  }

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

  dynamic "default_subnet_reference" {
    for_each = var.default_subnet_reference
    content {
      kind = default_subnet_reference.value["kind"]
      name = default_subnet_reference.value["name"]
      uuid = default_subnet_reference.value["uuid"]
    }
  }

  dynamic "environment_reference_list" {
    for_each = var.environment_reference_list
    content {
      kind = environment_reference_list.value["kind"]
      name = environment_reference_list.value["name"]
      uuid = environment_reference_list.value["uuid"]
    }
  }

  dynamic "external_network_list" {
    for_each = var.external_network_list
    content {
      name = external_network_list.value["name"]
      uuid = external_network_list.value["uuid"]
    }
  }

  dynamic "external_user_group_reference_list" {
    for_each = var.external_user_group_reference_list
    content {
      kind = external_user_group_reference_list.value["kind"]
      name = external_user_group_reference_list.value["name"]
      uuid = external_user_group_reference_list.value["uuid"]
    }
  }

  dynamic "resource_domain" {
    for_each = var.resource_domain
    content {

      dynamic "resources" {
        for_each = resource_domain.value.resources
        content {
          limit         = resources.value["limit"]
          resource_type = resources.value["resource_type"]
        }
      }

    }
  }

  dynamic "subnet_reference_list" {
    for_each = var.subnet_reference_list
    content {
      kind = subnet_reference_list.value["kind"]
      name = subnet_reference_list.value["name"]
      uuid = subnet_reference_list.value["uuid"]
    }
  }

  dynamic "user_reference_list" {
    for_each = var.user_reference_list
    content {
      kind = user_reference_list.value["kind"]
      name = user_reference_list.value["name"]
      uuid = user_reference_list.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_project.this.api_version
}

output "id" {
  description = "returns a string"
  value       = nutanix_project.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = nutanix_project.this.is_default
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_project.this.metadata
}

output "owner_reference" {
  description = "returns a map of string"
  value       = nutanix_project.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = nutanix_project.this.project_reference
}

output "state" {
  description = "returns a string"
  value       = nutanix_project.this.state
}

output "this" {
  value = nutanix_project.this
}
```

[top](#index)