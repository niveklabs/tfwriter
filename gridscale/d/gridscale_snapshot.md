# gridscale_snapshot

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
module "gridscale_snapshot" {
  source = "./modules/gridscale/d/gridscale_snapshot"

  # resource_id - (required) is a type of string
  resource_id = null
  # storage_uuid - (required) is a type of string
  storage_uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}

variable "storage_uuid" {
  description = "(required) - Uuid of the storage used to create this snapshot"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_snapshot" "this" {
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # storage_uuid - (required) is a type of string
  storage_uuid = var.storage_uuid
}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a number"
  value       = data.gridscale_snapshot.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_snapshot.this.current_price
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.id
}

output "labels" {
  description = "returns a list of string"
  value       = data.gridscale_snapshot.this.labels
}

output "license_product_no" {
  description = "returns a number"
  value       = data.gridscale_snapshot.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.name
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_snapshot.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = data.gridscale_snapshot.this.usage_in_minutes
}

output "this" {
  value = gridscale_snapshot.this
}
```

[top](#index)