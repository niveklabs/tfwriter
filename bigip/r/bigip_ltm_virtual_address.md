# bigip_ltm_virtual_address

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_virtual_address" {
  source = "./modules/bigip/r/bigip_ltm_virtual_address"

  # advertize_route - (optional) is a type of string
  advertize_route = null
  # arp - (optional) is a type of bool
  arp = null
  # auto_delete - (optional) is a type of bool
  auto_delete = null
  # conn_limit - (optional) is a type of number
  conn_limit = null
  # enabled - (optional) is a type of bool
  enabled = null
  # icmp_echo - (optional) is a type of bool
  icmp_echo = null
  # name - (required) is a type of string
  name = null
  # traffic_group - (optional) is a type of string
  traffic_group = null
}
```

[top](#index)

### Variables

```terraform
variable "advertize_route" {
  description = "(optional) - Enabled dynamic routing of the address"
  type        = string
  default     = null
}

variable "arp" {
  description = "(optional) - Enable or disable ARP for the virtual address"
  type        = bool
  default     = null
}

variable "auto_delete" {
  description = "(optional) - Automatically delete the virtual address with the virtual server"
  type        = bool
  default     = null
}

variable "conn_limit" {
  description = "(optional) - Max number of connections for virtual address"
  type        = number
  default     = null
}

variable "enabled" {
  description = "(optional) - Enable or disable the virtual address"
  type        = bool
  default     = null
}

variable "icmp_echo" {
  description = "(optional) - Enable/Disable ICMP response to the virtual address"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the virtual address"
  type        = string
}

variable "traffic_group" {
  description = "(optional) - Specify the partition and traffic group"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_virtual_address" "this" {
  advertize_route = var.advertize_route
  arp             = var.arp
  auto_delete     = var.auto_delete
  conn_limit      = var.conn_limit
  enabled         = var.enabled
  icmp_echo       = var.icmp_echo
  name            = var.name
  traffic_group   = var.traffic_group
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ltm_virtual_address.this.id
}

output "this" {
  value = bigip_ltm_virtual_address.this
}
```

[top](#index)