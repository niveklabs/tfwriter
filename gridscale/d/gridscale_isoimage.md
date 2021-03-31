# gridscale_isoimage

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
module "gridscale_isoimage" {
  source = "./modules/gridscale/d/gridscale_isoimage"

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
data "gridscale_isoimage" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a number"
  value       = data.gridscale_isoimage.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_isoimage.this.current_price
}

output "description" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.description
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_isoimage.this.labels
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.name
}

output "private" {
  description = "returns a bool"
  value       = data.gridscale_isoimage.this.private
}

output "server" {
  description = "returns a set of object"
  value       = data.gridscale_isoimage.this.server
}

output "source_url" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.source_url
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = data.gridscale_isoimage.this.usage_in_minutes
}

output "version" {
  description = "returns a string"
  value       = data.gridscale_isoimage.this.version
}

output "this" {
  value = gridscale_isoimage.this
}
```

[top](#index)