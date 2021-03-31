# opc_compute_ip_address_reservation

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_ip_address_reservation" {
  source = "./modules/opc/d/opc_compute_ip_address_reservation"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opc_compute_ip_address_reservation" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.opc_compute_ip_address_reservation.this.description
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_ip_address_reservation.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.opc_compute_ip_address_reservation.this.ip_address
}

output "ip_address_pool" {
  description = "returns a string"
  value       = data.opc_compute_ip_address_reservation.this.ip_address_pool
}

output "tags" {
  description = "returns a list of string"
  value       = data.opc_compute_ip_address_reservation.this.tags
}

output "uri" {
  description = "returns a string"
  value       = data.opc_compute_ip_address_reservation.this.uri
}

output "this" {
  value = opc_compute_ip_address_reservation.this
}
```

[top](#index)