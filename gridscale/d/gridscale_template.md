# gridscale_template

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
module "gridscale_template" {
  source = "./modules/gridscale/d/gridscale_template"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - name of the domain"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_template" "this" {
  labels = var.labels
  name   = var.name
}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a number"
  value       = data.gridscale_template.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_template.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_template.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_template.this.current_price
}

output "description" {
  description = "returns a string"
  value       = data.gridscale_template.this.description
}

output "distro" {
  description = "returns a string"
  value       = data.gridscale_template.this.distro
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_template.this.id
}

output "license_product_no" {
  description = "returns a number"
  value       = data.gridscale_template.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_template.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_template.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_template.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_template.this.location_uuid
}

output "ostype" {
  description = "returns a string"
  value       = data.gridscale_template.this.ostype
}

output "private" {
  description = "returns a bool"
  value       = data.gridscale_template.this.private
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_template.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = data.gridscale_template.this.usage_in_minutes
}

output "version" {
  description = "returns a string"
  value       = data.gridscale_template.this.version
}

output "this" {
  value = gridscale_template.this
}
```

[top](#index)