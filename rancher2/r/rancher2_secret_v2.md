# rancher2_secret_v2

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
module "rancher2_secret_v2" {
  source = "./modules/rancher2/r/rancher2_secret_v2"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # data - (required) is a type of map of string
  data = {}
  # immutable - (optional) is a type of bool
  immutable = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # type - (optional) is a type of string
  type = null

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

variable "cluster_id" {
  description = "(required) - K8s cluster ID"
  type        = string
}

variable "data" {
  description = "(required) - Secret data map"
  type        = map(string)
}

variable "immutable" {
  description = "(optional) - If set to true, ensures that data stored in the Secret cannot be updated"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - K8s Secret name"
  type        = string
}

variable "namespace" {
  description = "(optional) - K8s Secret namespace"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Used to facilitate programmatic handling of Secret data"
  type        = string
  default     = null
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
resource "rancher2_secret_v2" "this" {
  annotations = var.annotations
  cluster_id  = var.cluster_id
  data        = var.data
  immutable   = var.immutable
  labels      = var.labels
  name        = var.name
  namespace   = var.namespace
  type        = var.type

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
  value       = rancher2_secret_v2.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_secret_v2.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_secret_v2.this.labels
}

output "resource_version" {
  description = "returns a string"
  value       = rancher2_secret_v2.this.resource_version
}

output "this" {
  value = rancher2_secret_v2.this
}
```

[top](#index)