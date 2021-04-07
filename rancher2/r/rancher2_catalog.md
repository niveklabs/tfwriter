# rancher2_catalog

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
module "rancher2_catalog" {
  source = "./modules/rancher2/r/rancher2_catalog"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # branch - (optional) is a type of string
  branch = null
  # cluster_id - (optional) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # kind - (optional) is a type of string
  kind = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # project_id - (optional) is a type of string
  project_id = null
  # refresh - (optional) is a type of bool
  refresh = null
  # scope - (optional) is a type of string
  scope = null
  # url - (required) is a type of string
  url = null
  # username - (optional) is a type of string
  username = null
  # version - (optional) is a type of string
  version = null

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

variable "branch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kind" {
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

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refresh" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
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
resource "rancher2_catalog" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # branch - (optional) is a type of string
  branch = var.branch
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # description - (optional) is a type of string
  description = var.description
  # kind - (optional) is a type of string
  kind = var.kind
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # refresh - (optional) is a type of bool
  refresh = var.refresh
  # scope - (optional) is a type of string
  scope = var.scope
  # url - (required) is a type of string
  url = var.url
  # username - (optional) is a type of string
  username = var.username
  # version - (optional) is a type of string
  version = var.version

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
  value       = rancher2_catalog.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_catalog.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_catalog.this.labels
}

output "version" {
  description = "returns a string"
  value       = rancher2_catalog.this.version
}

output "this" {
  value = rancher2_catalog.this
}
```

[top](#index)