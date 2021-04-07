# rancher2_user

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
module "rancher2_user" {
  source = "./modules/rancher2/r/rancher2_user"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # enabled - (optional) is a type of bool
  enabled = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # username - (required) is a type of string
  username = null

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

variable "enabled" {
  description = "(optional)"
  type        = bool
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

variable "password" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
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
resource "rancher2_user" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (optional) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # username - (required) is a type of string
  username = var.username

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
  value       = rancher2_user.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_user.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_user.this.labels
}

output "principal_ids" {
  description = "returns a list of string"
  value       = rancher2_user.this.principal_ids
}

output "this" {
  value = rancher2_user.this
}
```

[top](#index)