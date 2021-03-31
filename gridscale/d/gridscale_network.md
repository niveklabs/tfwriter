# gridscale_network

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
module "gridscale_network" {
  source = "./modules/gridscale/d/gridscale_network"

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
data "gridscale_network" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_network.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_network.this.create_time
}

output "delete_block" {
  description = "returns a bool"
  value       = data.gridscale_network.this.delete_block
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_network.this.id
}

output "l2security" {
  description = "returns a bool"
  value       = data.gridscale_network.this.l2security
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_network.this.labels
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_network.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_network.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_network.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_network.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_network.this.name
}

output "network_type" {
  description = "returns a string"
  value       = data.gridscale_network.this.network_type
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_network.this.status
}

output "this" {
  value = gridscale_network.this
}
```

[top](#index)