# gridscale_firewall

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
module "gridscale_firewall" {
  source = "./modules/gridscale/d/gridscale_firewall"

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
data "gridscale_firewall" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.create_time
}

output "description" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.description
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_firewall.this.labels
}

output "location_name" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.location_name
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.name
}

output "network" {
  description = "returns a set of object"
  value       = data.gridscale_firewall.this.network
}

output "private" {
  description = "returns a bool"
  value       = data.gridscale_firewall.this.private
}

output "rules_v4_in" {
  description = "returns a list of object"
  value       = data.gridscale_firewall.this.rules_v4_in
}

output "rules_v4_out" {
  description = "returns a list of object"
  value       = data.gridscale_firewall.this.rules_v4_out
}

output "rules_v6_in" {
  description = "returns a list of object"
  value       = data.gridscale_firewall.this.rules_v6_in
}

output "rules_v6_out" {
  description = "returns a list of object"
  value       = data.gridscale_firewall.this.rules_v6_out
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_firewall.this.status
}

output "this" {
  value = gridscale_firewall.this
}
```

[top](#index)