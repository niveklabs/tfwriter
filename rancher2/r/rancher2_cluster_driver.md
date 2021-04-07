# rancher2_cluster_driver

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
module "rancher2_cluster_driver" {
  source = "./modules/rancher2/r/rancher2_cluster_driver"

  # active - (required) is a type of bool
  active = null
  # actual_url - (optional) is a type of string
  actual_url = null
  # annotations - (optional) is a type of map of string
  annotations = {}
  # builtin - (required) is a type of bool
  builtin = null
  # checksum - (optional) is a type of string
  checksum = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # ui_url - (optional) is a type of string
  ui_url = null
  # url - (required) is a type of string
  url = null
  # whitelist_domains - (optional) is a type of list of string
  whitelist_domains = []

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
variable "active" {
  description = "(required)"
  type        = bool
}

variable "actual_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "builtin" {
  description = "(required)"
  type        = bool
}

variable "checksum" {
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

variable "ui_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "whitelist_domains" {
  description = "(optional)"
  type        = list(string)
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
resource "rancher2_cluster_driver" "this" {
  # active - (required) is a type of bool
  active = var.active
  # actual_url - (optional) is a type of string
  actual_url = var.actual_url
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # builtin - (required) is a type of bool
  builtin = var.builtin
  # checksum - (optional) is a type of string
  checksum = var.checksum
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # ui_url - (optional) is a type of string
  ui_url = var.ui_url
  # url - (required) is a type of string
  url = var.url
  # whitelist_domains - (optional) is a type of list of string
  whitelist_domains = var.whitelist_domains

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
  value       = rancher2_cluster_driver.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster_driver.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cluster_driver.this.labels
}

output "this" {
  value = rancher2_cluster_driver.this
}
```

[top](#index)