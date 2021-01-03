# packet_device

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
module "packet_device" {
  source = "./modules/packet/d/packet_device"

  # device_id - (optional) is a type of string
  device_id = null
  # hostname - (optional) is a type of string
  hostname = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "device_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "packet_device" "this" {
  device_id  = var.device_id
  hostname   = var.hostname
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "access_private_ipv4" {
  description = "returns a string"
  value       = data.packet_device.this.access_private_ipv4
}

output "access_public_ipv4" {
  description = "returns a string"
  value       = data.packet_device.this.access_public_ipv4
}

output "access_public_ipv6" {
  description = "returns a string"
  value       = data.packet_device.this.access_public_ipv6
}

output "always_pxe" {
  description = "returns a bool"
  value       = data.packet_device.this.always_pxe
}

output "billing_cycle" {
  description = "returns a string"
  value       = data.packet_device.this.billing_cycle
}

output "description" {
  description = "returns a string"
  value       = data.packet_device.this.description
}

output "device_id" {
  description = "returns a string"
  value       = data.packet_device.this.device_id
}

output "facility" {
  description = "returns a string"
  value       = data.packet_device.this.facility
}

output "hardware_reservation_id" {
  description = "returns a string"
  value       = data.packet_device.this.hardware_reservation_id
}

output "hostname" {
  description = "returns a string"
  value       = data.packet_device.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.packet_device.this.id
}

output "ipxe_script_url" {
  description = "returns a string"
  value       = data.packet_device.this.ipxe_script_url
}

output "network" {
  description = "returns a list of object"
  value       = data.packet_device.this.network
}

output "network_type" {
  description = "returns a string"
  value       = data.packet_device.this.network_type
}

output "operating_system" {
  description = "returns a string"
  value       = data.packet_device.this.operating_system
}

output "plan" {
  description = "returns a string"
  value       = data.packet_device.this.plan
}

output "ports" {
  description = "returns a list of object"
  value       = data.packet_device.this.ports
}

output "project_id" {
  description = "returns a string"
  value       = data.packet_device.this.project_id
}

output "root_password" {
  description = "returns a string"
  value       = data.packet_device.this.root_password
  sensitive   = true
}

output "ssh_key_ids" {
  description = "returns a list of string"
  value       = data.packet_device.this.ssh_key_ids
}

output "state" {
  description = "returns a string"
  value       = data.packet_device.this.state
}

output "storage" {
  description = "returns a string"
  value       = data.packet_device.this.storage
}

output "tags" {
  description = "returns a list of string"
  value       = data.packet_device.this.tags
}

output "this" {
  value = packet_device.this
}
```

[top](#index)