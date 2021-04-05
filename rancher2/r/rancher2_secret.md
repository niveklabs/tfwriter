# rancher2_secret

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
module "rancher2_secret" {
  source = "./modules/rancher2/r/rancher2_secret"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # data - (required) is a type of map of string
  data = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # project_id - (required) is a type of string
  project_id = null

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

variable "data" {
  description = "(required) - Secret data base64 encoded"
  type        = map(string)
}

variable "description" {
  description = "(optional) - Secret description"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - Secret name"
  type        = string
  default     = null
}

variable "namespace_id" {
  description = "(optional) - Namespace ID to add secret"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - Project ID to add secret"
  type        = string
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
resource "rancher2_secret" "this" {
  annotations  = var.annotations
  data         = var.data
  description  = var.description
  labels       = var.labels
  name         = var.name
  namespace_id = var.namespace_id
  project_id   = var.project_id

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
  value       = rancher2_secret.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_secret.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_secret.this.labels
}

output "this" {
  value = rancher2_secret.this
}
```

[top](#index)