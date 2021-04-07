# packet_volume

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
module "packet_volume" {
  source = "./modules/packet/d/packet_volume"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # volume_id - (optional) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "packet_volume" "this" {
  # name - (optional) is a type of string
  name = var.name
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # volume_id - (optional) is a type of string
  volume_id = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "billing_cycle" {
  description = "returns a string"
  value       = data.packet_volume.this.billing_cycle
}

output "created" {
  description = "returns a string"
  value       = data.packet_volume.this.created
}

output "description" {
  description = "returns a string"
  value       = data.packet_volume.this.description
}

output "device_ids" {
  description = "returns a list of string"
  value       = data.packet_volume.this.device_ids
}

output "facility" {
  description = "returns a string"
  value       = data.packet_volume.this.facility
}

output "id" {
  description = "returns a string"
  value       = data.packet_volume.this.id
}

output "locked" {
  description = "returns a bool"
  value       = data.packet_volume.this.locked
}

output "name" {
  description = "returns a string"
  value       = data.packet_volume.this.name
}

output "plan" {
  description = "returns a string"
  value       = data.packet_volume.this.plan
}

output "project_id" {
  description = "returns a string"
  value       = data.packet_volume.this.project_id
}

output "size" {
  description = "returns a number"
  value       = data.packet_volume.this.size
}

output "snapshot_policies" {
  description = "returns a list of object"
  value       = data.packet_volume.this.snapshot_policies
}

output "state" {
  description = "returns a string"
  value       = data.packet_volume.this.state
}

output "updated" {
  description = "returns a string"
  value       = data.packet_volume.this.updated
}

output "volume_id" {
  description = "returns a string"
  value       = data.packet_volume.this.volume_id
}

output "this" {
  value = packet_volume.this
}
```

[top](#index)