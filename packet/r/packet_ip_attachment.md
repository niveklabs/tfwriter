# packet_ip_attachment

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
module "packet_ip_attachment" {
  source = "./modules/packet/r/packet_ip_attachment"

  # cidr_notation - (required) is a type of string
  cidr_notation = null
  # device_id - (required) is a type of string
  device_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_notation" {
  description = "(required)"
  type        = string
}

variable "device_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "packet_ip_attachment" "this" {
  cidr_notation = var.cidr_notation
  device_id     = var.device_id
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = packet_ip_attachment.this.address
}

output "address_family" {
  description = "returns a number"
  value       = packet_ip_attachment.this.address_family
}

output "cidr" {
  description = "returns a number"
  value       = packet_ip_attachment.this.cidr
}

output "gateway" {
  description = "returns a string"
  value       = packet_ip_attachment.this.gateway
}

output "global" {
  description = "returns a bool"
  value       = packet_ip_attachment.this.global
}

output "id" {
  description = "returns a string"
  value       = packet_ip_attachment.this.id
}

output "manageable" {
  description = "returns a bool"
  value       = packet_ip_attachment.this.manageable
}

output "management" {
  description = "returns a bool"
  value       = packet_ip_attachment.this.management
}

output "netmask" {
  description = "returns a string"
  value       = packet_ip_attachment.this.netmask
}

output "network" {
  description = "returns a string"
  value       = packet_ip_attachment.this.network
}

output "public" {
  description = "returns a bool"
  value       = packet_ip_attachment.this.public
}

output "this" {
  value = packet_ip_attachment.this
}
```

[top](#index)