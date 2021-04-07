# rancher2_cluster_role_template_binding

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
module "rancher2_cluster_role_template_binding" {
  source = "./modules/rancher2/r/rancher2_cluster_role_template_binding"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # group_id - (optional) is a type of string
  group_id = null
  # group_principal_id - (optional) is a type of string
  group_principal_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # role_template_id - (required) is a type of string
  role_template_id = null
  # user_id - (optional) is a type of string
  user_id = null
  # user_principal_id - (optional) is a type of string
  user_principal_id = null

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
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
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
  description = "(required)"
  type        = string
}

variable "role_template_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_principal_id" {
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
resource "rancher2_cluster_role_template_binding" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # group_principal_id - (optional) is a type of string
  group_principal_id = var.group_principal_id
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # role_template_id - (required) is a type of string
  role_template_id = var.role_template_id
  # user_id - (optional) is a type of string
  user_id = var.user_id
  # user_principal_id - (optional) is a type of string
  user_principal_id = var.user_principal_id

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
  value       = rancher2_cluster_role_template_binding.this.annotations
}

output "group_principal_id" {
  description = "returns a string"
  value       = rancher2_cluster_role_template_binding.this.group_principal_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster_role_template_binding.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cluster_role_template_binding.this.labels
}

output "user_principal_id" {
  description = "returns a string"
  value       = rancher2_cluster_role_template_binding.this.user_principal_id
}

output "this" {
  value = rancher2_cluster_role_template_binding.this
}
```

[top](#index)