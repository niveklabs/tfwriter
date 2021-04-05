# rancher2_registry

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
module "rancher2_registry" {
  source = "./modules/rancher2/r/rancher2_registry"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # project_id - (required) is a type of string
  project_id = null

  registries = [{
    address  = null
    password = null
    username = null
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
  description = "(optional) - Description of the docker registry"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the docker registry"
  type        = string
}

variable "namespace_id" {
  description = "(optional) - Namespace ID to add docker registry"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - Project ID to add docker registry"
  type        = string
}

variable "registries" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      address  = string
      password = string
      username = string
    }
  ))
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
resource "rancher2_registry" "this" {
  annotations  = var.annotations
  description  = var.description
  labels       = var.labels
  name         = var.name
  namespace_id = var.namespace_id
  project_id   = var.project_id

  dynamic "registries" {
    for_each = var.registries
    content {
      address  = registries.value["address"]
      password = registries.value["password"]
      username = registries.value["username"]
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
  value       = rancher2_registry.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_registry.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_registry.this.labels
}

output "this" {
  value = rancher2_registry.this
}
```

[top](#index)