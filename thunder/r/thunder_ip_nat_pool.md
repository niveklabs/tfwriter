# thunder_ip_nat_pool

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_ip_nat_pool" {
  source = "./modules/thunder/r/thunder_ip_nat_pool"

  # chunk_netmask - (optional) is a type of string
  chunk_netmask = null
  # end_address - (optional) is a type of string
  end_address = null
  # ethernet - (optional) is a type of number
  ethernet = null
  # gateway - (optional) is a type of string
  gateway = null
  # ip_rr - (optional) is a type of number
  ip_rr = null
  # netmask - (optional) is a type of string
  netmask = null
  # pool_name - (optional) is a type of string
  pool_name = null
  # port_overload - (optional) is a type of number
  port_overload = null
  # scaleout_device_id - (optional) is a type of number
  scaleout_device_id = null
  # start_address - (optional) is a type of string
  start_address = null
  # use_if_ip - (optional) is a type of number
  use_if_ip = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrid - (optional) is a type of number
  vrid = null
}
```

[top](#index)

### Variables

```terraform
variable "chunk_netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ethernet" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_rr" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_overload" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scaleout_device_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "start_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_if_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_ip_nat_pool" "this" {
  # chunk_netmask - (optional) is a type of string
  chunk_netmask = var.chunk_netmask
  # end_address - (optional) is a type of string
  end_address = var.end_address
  # ethernet - (optional) is a type of number
  ethernet = var.ethernet
  # gateway - (optional) is a type of string
  gateway = var.gateway
  # ip_rr - (optional) is a type of number
  ip_rr = var.ip_rr
  # netmask - (optional) is a type of string
  netmask = var.netmask
  # pool_name - (optional) is a type of string
  pool_name = var.pool_name
  # port_overload - (optional) is a type of number
  port_overload = var.port_overload
  # scaleout_device_id - (optional) is a type of number
  scaleout_device_id = var.scaleout_device_id
  # start_address - (optional) is a type of string
  start_address = var.start_address
  # use_if_ip - (optional) is a type of number
  use_if_ip = var.use_if_ip
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vrid - (optional) is a type of number
  vrid = var.vrid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_nat_pool.this.id
}

output "this" {
  value = thunder_ip_nat_pool.this
}
```

[top](#index)