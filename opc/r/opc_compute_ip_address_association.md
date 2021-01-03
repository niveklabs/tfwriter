# opc_compute_ip_address_association

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
module "opc_compute_ip_address_association" {
  source = "./modules/opc/r/opc_compute_ip_address_association"

  # description - (optional) is a type of string
  description = null
  # ip_address_reservation - (optional) is a type of string
  ip_address_reservation = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
  # vnic - (optional) is a type of string
  vnic = null
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

variable "ip_address_reservation" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "vnic" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_ip_address_association" "this" {
  description            = var.description
  ip_address_reservation = var.ip_address_reservation
  name                   = var.name
  tags                   = var.tags
  vnic                   = var.vnic
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ip_address_association.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_ip_address_association.this.uri
}

output "this" {
  value = opc_compute_ip_address_association.this
}
```

[top](#index)