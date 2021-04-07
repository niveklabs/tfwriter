# oci_load_balancer_backend

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
module "oci_load_balancer_backend" {
  source = "./modules/oci/r/oci_load_balancer_backend"

  # backendset_name - (required) is a type of string
  backendset_name = null
  # backup - (optional) is a type of bool
  backup = null
  # drain - (optional) is a type of bool
  drain = null
  # ip_address - (required) is a type of string
  ip_address = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # offline - (optional) is a type of bool
  offline = null
  # port - (required) is a type of number
  port = null
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
variable "backendset_name" {
  description = "(required)"
  type        = string
}

variable "backup" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "drain" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "offline" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
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
resource "oci_load_balancer_backend" "this" {
  backendset_name  = var.backendset_name
  backup           = var.backup
  drain            = var.drain
  ip_address       = var.ip_address
  load_balancer_id = var.load_balancer_id
  offline          = var.offline
  port             = var.port
  weight           = var.weight

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
output "drain" {
  description = "returns a bool"
  value       = oci_load_balancer_backend.this.drain
}

output "id" {
  description = "returns a string"
  value       = oci_load_balancer_backend.this.id
}

output "name" {
  description = "returns a string"
  value       = oci_load_balancer_backend.this.name
}

output "offline" {
  description = "returns a bool"
  value       = oci_load_balancer_backend.this.offline
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_backend.this.state
}

output "weight" {
  description = "returns a number"
  value       = oci_load_balancer_backend.this.weight
}

output "this" {
  value = oci_load_balancer_backend.this
}
```

[top](#index)