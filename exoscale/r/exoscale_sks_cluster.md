# exoscale_sks_cluster

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_sks_cluster" {
  source = "./modules/exoscale/r/exoscale_sks_cluster"

  # addons - (optional) is a type of set of string
  addons = []
  # cni - (optional) is a type of string
  cni = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # service_level - (optional) is a type of string
  service_level = null
  # version - (optional) is a type of string
  version = null
  # zone - (required) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "addons" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cni" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "service_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_sks_cluster" "this" {
  # addons - (optional) is a type of set of string
  addons = var.addons
  # cni - (optional) is a type of string
  cni = var.cni
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # service_level - (optional) is a type of string
  service_level = var.service_level
  # version - (optional) is a type of string
  version = var.version
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "addons" {
  description = "returns a set of string"
  value       = exoscale_sks_cluster.this.addons
}

output "created_at" {
  description = "returns a string"
  value       = exoscale_sks_cluster.this.created_at
}

output "endpoint" {
  description = "returns a string"
  value       = exoscale_sks_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = exoscale_sks_cluster.this.id
}

output "nodepools" {
  description = "returns a set of string"
  value       = exoscale_sks_cluster.this.nodepools
}

output "state" {
  description = "returns a string"
  value       = exoscale_sks_cluster.this.state
}

output "this" {
  value = exoscale_sks_cluster.this
}
```

[top](#index)