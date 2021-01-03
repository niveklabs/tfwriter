# packet_reserved_ip_block

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_reserved_ip_block" {
  source = "./modules/packet/r/packet_reserved_ip_block"

  # description - (optional) is a type of string
  description = null
  # facility - (optional) is a type of string
  facility = null
  # project_id - (required) is a type of string
  project_id = null
  # quantity - (required) is a type of number
  quantity = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "facility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "quantity" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "packet_reserved_ip_block" "this" {
  description = var.description
  facility    = var.facility
  project_id  = var.project_id
  quantity    = var.quantity
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = packet_reserved_ip_block.this.address
}

output "address_family" {
  description = "returns a number"
  value       = packet_reserved_ip_block.this.address_family
}

output "cidr" {
  description = "returns a number"
  value       = packet_reserved_ip_block.this.cidr
}

output "cidr_notation" {
  description = "returns a string"
  value       = packet_reserved_ip_block.this.cidr_notation
}

output "gateway" {
  description = "returns a string"
  value       = packet_reserved_ip_block.this.gateway
}

output "global" {
  description = "returns a bool"
  value       = packet_reserved_ip_block.this.global
}

output "id" {
  description = "returns a string"
  value       = packet_reserved_ip_block.this.id
}

output "manageable" {
  description = "returns a bool"
  value       = packet_reserved_ip_block.this.manageable
}

output "management" {
  description = "returns a bool"
  value       = packet_reserved_ip_block.this.management
}

output "netmask" {
  description = "returns a string"
  value       = packet_reserved_ip_block.this.netmask
}

output "network" {
  description = "returns a string"
  value       = packet_reserved_ip_block.this.network
}

output "public" {
  description = "returns a bool"
  value       = packet_reserved_ip_block.this.public
}

output "this" {
  value = packet_reserved_ip_block.this
}
```

[top](#index)