# exoscale_sks_nodepool

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
module "exoscale_sks_nodepool" {
  source = "./modules/exoscale/r/exoscale_sks_nodepool"

  # anti_affinity_group_ids - (optional) is a type of set of string
  anti_affinity_group_ids = []
  # cluster_id - (required) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # disk_size - (optional) is a type of number
  disk_size = null
  # instance_type - (required) is a type of string
  instance_type = null
  # name - (required) is a type of string
  name = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # size - (required) is a type of number
  size = null
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
variable "anti_affinity_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "size" {
  description = "(required)"
  type        = number
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
resource "exoscale_sks_nodepool" "this" {
  anti_affinity_group_ids = var.anti_affinity_group_ids
  cluster_id              = var.cluster_id
  description             = var.description
  disk_size               = var.disk_size
  instance_type           = var.instance_type
  name                    = var.name
  security_group_ids      = var.security_group_ids
  size                    = var.size
  zone                    = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = exoscale_sks_nodepool.this.created_at
}

output "id" {
  description = "returns a string"
  value       = exoscale_sks_nodepool.this.id
}

output "instance_pool_id" {
  description = "returns a string"
  value       = exoscale_sks_nodepool.this.instance_pool_id
}

output "state" {
  description = "returns a string"
  value       = exoscale_sks_nodepool.this.state
}

output "template_id" {
  description = "returns a string"
  value       = exoscale_sks_nodepool.this.template_id
}

output "version" {
  description = "returns a string"
  value       = exoscale_sks_nodepool.this.version
}

output "this" {
  value = exoscale_sks_nodepool.this
}
```

[top](#index)