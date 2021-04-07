# opc_compute_ip_reservation

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
module "opc_compute_ip_reservation" {
  source = "./modules/opc/d/opc_compute_ip_reservation"

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
data "opc_compute_ip_reservation" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.opc_compute_ip_reservation.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.opc_compute_ip_reservation.this.ip
}

output "parent_pool" {
  description = "returns a string"
  value       = data.opc_compute_ip_reservation.this.parent_pool
}

output "permanent" {
  description = "returns a bool"
  value       = data.opc_compute_ip_reservation.this.permanent
}

output "tags" {
  description = "returns a list of string"
  value       = data.opc_compute_ip_reservation.this.tags
}

output "used" {
  description = "returns a bool"
  value       = data.opc_compute_ip_reservation.this.used
}

output "this" {
  value = opc_compute_ip_reservation.this
}
```

[top](#index)