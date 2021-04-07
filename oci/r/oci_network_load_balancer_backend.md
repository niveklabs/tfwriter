# oci_network_load_balancer_backend

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_network_load_balancer_backend" {
  source = "./modules/oci/r/oci_network_load_balancer_backend"

  # backend_set_name - (required) is a type of string
  backend_set_name = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # is_backup - (optional) is a type of bool
  is_backup = null
  # is_drain - (optional) is a type of bool
  is_drain = null
  # is_offline - (optional) is a type of bool
  is_offline = null
  # name - (optional) is a type of string
  name = null
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
  # port - (required) is a type of number
  port = null
  # target_id - (optional) is a type of string
  target_id = null
  # weight - (optional) is a type of number
  weight = null

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
variable "backend_set_name" {
  description = "(required)"
  type        = string
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_backup" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_drain" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_offline" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "target_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
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
resource "oci_network_load_balancer_backend" "this" {
  # backend_set_name - (required) is a type of string
  backend_set_name = var.backend_set_name
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # is_backup - (optional) is a type of bool
  is_backup = var.is_backup
  # is_drain - (optional) is a type of bool
  is_drain = var.is_drain
  # is_offline - (optional) is a type of bool
  is_offline = var.is_offline
  # name - (optional) is a type of string
  name = var.name
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = var.network_load_balancer_id
  # port - (required) is a type of number
  port = var.port
  # target_id - (optional) is a type of string
  target_id = var.target_id
  # weight - (optional) is a type of number
  weight = var.weight

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
output "id" {
  description = "returns a string"
  value       = oci_network_load_balancer_backend.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_network_load_balancer_backend.this.ip_address
}

output "is_backup" {
  description = "returns a bool"
  value       = oci_network_load_balancer_backend.this.is_backup
}

output "is_drain" {
  description = "returns a bool"
  value       = oci_network_load_balancer_backend.this.is_drain
}

output "is_offline" {
  description = "returns a bool"
  value       = oci_network_load_balancer_backend.this.is_offline
}

output "name" {
  description = "returns a string"
  value       = oci_network_load_balancer_backend.this.name
}

output "target_id" {
  description = "returns a string"
  value       = oci_network_load_balancer_backend.this.target_id
}

output "weight" {
  description = "returns a number"
  value       = oci_network_load_balancer_backend.this.weight
}

output "this" {
  value = oci_network_load_balancer_backend.this
}
```

[top](#index)