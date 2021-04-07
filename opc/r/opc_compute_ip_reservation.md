# opc_compute_ip_reservation

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/opc/r/opc_compute_ip_reservation"

  # name - (optional) is a type of string
  name = null
  # parent_pool - (optional) is a type of string
  parent_pool = null
  # permanent - (required) is a type of bool
  permanent = null
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permanent" {
  description = "(required)"
  type        = bool
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_ip_reservation" "this" {
  # name - (optional) is a type of string
  name = var.name
  # parent_pool - (optional) is a type of string
  parent_pool = var.parent_pool
  # permanent - (required) is a type of bool
  permanent = var.permanent
  # tags - (optional) is a type of list of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ip_reservation.this.id
}

output "ip" {
  description = "returns a string"
  value       = opc_compute_ip_reservation.this.ip
}

output "name" {
  description = "returns a string"
  value       = opc_compute_ip_reservation.this.name
}

output "used" {
  description = "returns a bool"
  value       = opc_compute_ip_reservation.this.used
}

output "this" {
  value = opc_compute_ip_reservation.this
}
```

[top](#index)