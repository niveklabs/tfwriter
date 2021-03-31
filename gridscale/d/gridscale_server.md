# gridscale_server

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_server" {
  source = "./modules/gridscale/d/gridscale_server"

  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_server" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "auto_recovery" {
  description = "returns a bool"
  value       = data.gridscale_server.this.auto_recovery
}

output "availability_zone" {
  description = "returns a string"
  value       = data.gridscale_server.this.availability_zone
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_server.this.change_time
}

output "console_token" {
  description = "returns a string"
  value       = data.gridscale_server.this.console_token
}

output "cores" {
  description = "returns a number"
  value       = data.gridscale_server.this.cores
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_server.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_server.this.current_price
}

output "hardware_profile" {
  description = "returns a string"
  value       = data.gridscale_server.this.hardware_profile
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_server.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = data.gridscale_server.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = data.gridscale_server.this.ipv6
}

output "isoimage" {
  description = "returns a string"
  value       = data.gridscale_server.this.isoimage
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_server.this.labels
}

output "legacy" {
  description = "returns a bool"
  value       = data.gridscale_server.this.legacy
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_server.this.location_uuid
}

output "memory" {
  description = "returns a number"
  value       = data.gridscale_server.this.memory
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_server.this.name
}

output "network" {
  description = "returns a set of object"
  value       = data.gridscale_server.this.network
}

output "power" {
  description = "returns a bool"
  value       = data.gridscale_server.this.power
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_server.this.status
}

output "storage" {
  description = "returns a list of object"
  value       = data.gridscale_server.this.storage
}

output "usage_in_minutes_cores" {
  description = "returns a number"
  value       = data.gridscale_server.this.usage_in_minutes_cores
}

output "usage_in_minutes_memory" {
  description = "returns a number"
  value       = data.gridscale_server.this.usage_in_minutes_memory
}

output "this" {
  value = gridscale_server.this
}
```

[top](#index)