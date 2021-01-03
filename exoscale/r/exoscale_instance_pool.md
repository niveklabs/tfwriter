# exoscale_instance_pool

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
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_instance_pool" {
  source = "./modules/exoscale/r/exoscale_instance_pool"

  # affinity_group_ids - (optional) is a type of set of string
  affinity_group_ids = []
  # description - (optional) is a type of string
  description = null
  # disk_size - (optional) is a type of number
  disk_size = null
  # ipv6 - (optional) is a type of bool
  ipv6 = null
  # key_pair - (optional) is a type of string
  key_pair = null
  # name - (required) is a type of string
  name = null
  # network_ids - (optional) is a type of set of string
  network_ids = []
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # service_offering - (required) is a type of string
  service_offering = null
  # size - (required) is a type of number
  size = null
  # state - (optional) is a type of string
  state = null
  # template_id - (required) is a type of string
  template_id = null
  # user_data - (optional) is a type of string
  user_data = null
  # virtual_machines - (optional) is a type of set of string
  virtual_machines = []
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
variable "affinity_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
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

variable "ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_pair" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "service_offering" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_id" {
  description = "(required)"
  type        = string
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_machines" {
  description = "(optional)"
  type        = set(string)
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
resource "exoscale_instance_pool" "this" {
  affinity_group_ids = var.affinity_group_ids
  description        = var.description
  disk_size          = var.disk_size
  ipv6               = var.ipv6
  key_pair           = var.key_pair
  name               = var.name
  network_ids        = var.network_ids
  security_group_ids = var.security_group_ids
  service_offering   = var.service_offering
  size               = var.size
  state              = var.state
  template_id        = var.template_id
  user_data          = var.user_data
  virtual_machines   = var.virtual_machines
  zone               = var.zone

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
output "disk_size" {
  description = "returns a number"
  value       = exoscale_instance_pool.this.disk_size
}

output "id" {
  description = "returns a string"
  value       = exoscale_instance_pool.this.id
}

output "state" {
  description = "returns a string"
  value       = exoscale_instance_pool.this.state
}

output "virtual_machines" {
  description = "returns a set of string"
  value       = exoscale_instance_pool.this.virtual_machines
}

output "this" {
  value = exoscale_instance_pool.this
}
```

[top](#index)