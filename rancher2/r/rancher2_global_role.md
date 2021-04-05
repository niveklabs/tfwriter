# rancher2_global_role

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_global_role" {
  source = "./modules/rancher2/r/rancher2_global_role"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # new_user_default - (optional) is a type of bool
  new_user_default = null

  rules = [{
    api_groups        = []
    non_resource_urls = []
    resource_names    = []
    resources         = []
    verbs             = []
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - Global role policy description"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Global role policy name"
  type        = string
}

variable "new_user_default" {
  description = "(optional) - Whether or not this role should be added to new users"
  type        = bool
  default     = null
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      api_groups        = list(string)
      non_resource_urls = list(string)
      resource_names    = list(string)
      resources         = list(string)
      verbs             = list(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_global_role" "this" {
  annotations      = var.annotations
  description      = var.description
  labels           = var.labels
  name             = var.name
  new_user_default = var.new_user_default

  dynamic "rules" {
    for_each = var.rules
    content {
      api_groups        = rules.value["api_groups"]
      non_resource_urls = rules.value["non_resource_urls"]
      resource_names    = rules.value["resource_names"]
      resources         = rules.value["resources"]
      verbs             = rules.value["verbs"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_global_role.this.annotations
}

output "builtin" {
  description = "returns a bool"
  value       = rancher2_global_role.this.builtin
}

output "description" {
  description = "returns a string"
  value       = rancher2_global_role.this.description
}

output "id" {
  description = "returns a string"
  value       = rancher2_global_role.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_global_role.this.labels
}

output "this" {
  value = rancher2_global_role.this
}
```

[top](#index)