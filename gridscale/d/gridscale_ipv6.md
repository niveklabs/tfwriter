# gridscale_ipv6

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
module "gridscale_ipv6" {
  source = "./modules/gridscale/d/gridscale_ipv6"

  # labels - (optional) is a type of set of string
  labels = []
  # resource_id - (required) is a type of string
  resource_id = null
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

variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_ipv6" "this" {
  # labels - (optional) is a type of set of string
  labels = var.labels
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = data.gridscale_ipv6.this.current_price
}

output "delete_block" {
  description = "returns a bool"
  value       = data.gridscale_ipv6.this.delete_block
}

output "failover" {
  description = "returns a bool"
  value       = data.gridscale_ipv6.this.failover
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.ip
}

output "location_country" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.name
}

output "prefix" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.prefix
}

output "reverse_dns" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.reverse_dns
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_ipv6.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = data.gridscale_ipv6.this.usage_in_minutes
}

output "this" {
  value = gridscale_ipv6.this
}
```

[top](#index)