# gridscale_storage

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
module "gridscale_storage" {
  source = "./modules/gridscale/d/gridscale_storage"

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
data "gridscale_storage" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a number"
  value       = data.gridscale_storage.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_storage.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_storage.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_storage.this.current_price
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_storage.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_storage.this.labels
}

output "last_used_template" {
  description = "returns a string"
  value       = data.gridscale_storage.this.last_used_template
}

output "license_product_no" {
  description = "returns a number"
  value       = data.gridscale_storage.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_storage.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_storage.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_storage.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_storage.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_storage.this.name
}

output "parent_uuid" {
  description = "returns a string"
  value       = data.gridscale_storage.this.parent_uuid
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_storage.this.status
}

output "storage_type" {
  description = "returns a string"
  value       = data.gridscale_storage.this.storage_type
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = data.gridscale_storage.this.usage_in_minutes
}

output "this" {
  value = gridscale_storage.this
}
```

[top](#index)