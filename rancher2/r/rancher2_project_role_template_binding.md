# rancher2_project_role_template_binding

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
module "rancher2_project_role_template_binding" {
  source = "./modules/rancher2/r/rancher2_project_role_template_binding"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # group_id - (optional) is a type of string
  group_id = null
  # group_principal_id - (optional) is a type of string
  group_principal_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
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

variable "project_id" {
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
resource "rancher2_project_role_template_binding" "this" {
  annotations        = var.annotations
  group_id           = var.group_id
  group_principal_id = var.group_principal_id
  labels             = var.labels
  name               = var.name
  project_id         = var.project_id
  role_template_id   = var.role_template_id
  user_id            = var.user_id
  user_principal_id  = var.user_principal_id

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
  value       = rancher2_project_role_template_binding.this.annotations
}

output "group_principal_id" {
  description = "returns a string"
  value       = rancher2_project_role_template_binding.this.group_principal_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_project_role_template_binding.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_project_role_template_binding.this.labels
}

output "user_principal_id" {
  description = "returns a string"
  value       = rancher2_project_role_template_binding.this.user_principal_id
}

output "this" {
  value = rancher2_project_role_template_binding.this
}
```

[top](#index)