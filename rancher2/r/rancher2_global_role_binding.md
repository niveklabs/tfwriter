# rancher2_global_role_binding

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
module "rancher2_global_role_binding" {
  source = "./modules/rancher2/r/rancher2_global_role_binding"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # global_role_id - (required) is a type of string
  global_role_id = null
  # group_principal_id - (optional) is a type of string
  group_principal_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # user_id - (optional) is a type of string
  user_id = null

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

variable "global_role_id" {
  description = "(required)"
  type        = string
}

variable "group_principal_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
  description = "(optional)"
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
resource "rancher2_global_role_binding" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # global_role_id - (required) is a type of string
  global_role_id = var.global_role_id
  # group_principal_id - (optional) is a type of string
  group_principal_id = var.group_principal_id
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (optional) is a type of string
  name = var.name
  # user_id - (optional) is a type of string
  user_id = var.user_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = rancher2_global_role_binding.this.annotations
}

output "group_principal_id" {
  description = "returns a string"
  value       = rancher2_global_role_binding.this.group_principal_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_global_role_binding.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_global_role_binding.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_global_role_binding.this.name
}

output "user_id" {
  description = "returns a string"
  value       = rancher2_global_role_binding.this.user_id
}

output "this" {
  value = rancher2_global_role_binding.this
}
```

[top](#index)