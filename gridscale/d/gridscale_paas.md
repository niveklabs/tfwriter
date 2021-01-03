# gridscale_paas

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
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_paas" {
  source = "./modules/gridscale/d/gridscale_paas"

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
data "gridscale_paas" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_paas.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_paas.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_paas.this.current_price
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_paas.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_paas.this.labels
}

output "listen_port" {
  description = "returns a set of object"
  value       = data.gridscale_paas.this.listen_port
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_paas.this.name
}

output "network_uuid" {
  description = "returns a string"
  value       = data.gridscale_paas.this.network_uuid
}

output "parameter" {
  description = "returns a set of object"
  value       = data.gridscale_paas.this.parameter
}

output "password" {
  description = "returns a string"
  value       = data.gridscale_paas.this.password
}

output "resource_limit" {
  description = "returns a set of object"
  value       = data.gridscale_paas.this.resource_limit
}

output "security_zone_uuid" {
  description = "returns a string"
  value       = data.gridscale_paas.this.security_zone_uuid
}

output "service_template_uuid" {
  description = "returns a string"
  value       = data.gridscale_paas.this.service_template_uuid
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_paas.this.status
}

output "usage_in_minute" {
  description = "returns a number"
  value       = data.gridscale_paas.this.usage_in_minute
}

output "username" {
  description = "returns a string"
  value       = data.gridscale_paas.this.username
}

output "this" {
  value = gridscale_paas.this
}
```

[top](#index)