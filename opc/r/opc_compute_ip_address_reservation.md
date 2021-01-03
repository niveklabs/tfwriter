# opc_compute_ip_address_reservation

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
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_ip_address_reservation" {
  source = "./modules/opc/r/opc_compute_ip_address_reservation"

  # description - (optional) is a type of string
  description = null
  # ip_address_pool - (required) is a type of string
  ip_address_pool = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address_pool" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "opc_compute_ip_address_reservation" "this" {
  description     = var.description
  ip_address_pool = var.ip_address_pool
  name            = var.name
  tags            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ip_address_reservation.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = opc_compute_ip_address_reservation.this.ip_address
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_ip_address_reservation.this.uri
}

output "this" {
  value = opc_compute_ip_address_reservation.this
}
```

[top](#index)