# gridscale_paas_securityzone

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
module "gridscale_paas_securityzone" {
  source = "./modules/gridscale/d/gridscale_paas_securityzone"

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
data "gridscale_paas_securityzone" "this" {
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.create_time
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_paas_securityzone.this.labels
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.name
}

output "relations" {
  description = "returns a set of string"
  value       = data.gridscale_paas_securityzone.this.relations
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_paas_securityzone.this.status
}

output "this" {
  value = gridscale_paas_securityzone.this
}
```

[top](#index)