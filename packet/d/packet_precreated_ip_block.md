# packet_precreated_ip_block

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "packet_precreated_ip_block" {
  source = "./modules/packet/d/packet_precreated_ip_block"

  # address_family - (required) is a type of number
  address_family = null
  # facility - (optional) is a type of string
  facility = null
  # global - (optional) is a type of bool
  global = null
  # project_id - (required) is a type of string
  project_id = null
  # public - (required) is a type of bool
  public = null
}
```

[top](#index)

### Variables

```terraform
variable "address_family" {
  description = "(required)"
  type        = number
}

variable "facility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "public" {
  description = "(required)"
  type        = bool
}
```

[top](#index)

### Datasource

```terraform
data "packet_precreated_ip_block" "this" {
  # address_family - (required) is a type of number
  address_family = var.address_family
  # facility - (optional) is a type of string
  facility = var.facility
  # global - (optional) is a type of bool
  global = var.global
  # project_id - (required) is a type of string
  project_id = var.project_id
  # public - (required) is a type of bool
  public = var.public
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.address
}

output "cidr" {
  description = "returns a number"
  value       = data.packet_precreated_ip_block.this.cidr
}

output "cidr_notation" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.cidr_notation
}

output "gateway" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.id
}

output "manageable" {
  description = "returns a bool"
  value       = data.packet_precreated_ip_block.this.manageable
}

output "management" {
  description = "returns a bool"
  value       = data.packet_precreated_ip_block.this.management
}

output "netmask" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.netmask
}

output "network" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.network
}

output "quantity" {
  description = "returns a number"
  value       = data.packet_precreated_ip_block.this.quantity
}

output "type" {
  description = "returns a string"
  value       = data.packet_precreated_ip_block.this.type
}

output "this" {
  value = packet_precreated_ip_block.this
}
```

[top](#index)