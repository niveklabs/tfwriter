# opc_compute_route

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
module "opc_compute_route" {
  source = "./modules/opc/r/opc_compute_route"

  # admin_distance - (optional) is a type of number
  admin_distance = null
  # description - (optional) is a type of string
  description = null
  # ip_address_prefix - (required) is a type of string
  ip_address_prefix = null
  # name - (required) is a type of string
  name = null
  # next_hop_vnic_set - (required) is a type of string
  next_hop_vnic_set = null
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "admin_distance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address_prefix" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "next_hop_vnic_set" {
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
resource "opc_compute_route" "this" {
  # admin_distance - (optional) is a type of number
  admin_distance = var.admin_distance
  # description - (optional) is a type of string
  description = var.description
  # ip_address_prefix - (required) is a type of string
  ip_address_prefix = var.ip_address_prefix
  # name - (required) is a type of string
  name = var.name
  # next_hop_vnic_set - (required) is a type of string
  next_hop_vnic_set = var.next_hop_vnic_set
  # tags - (optional) is a type of list of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_route.this.id
}

output "this" {
  value = opc_compute_route.this
}
```

[top](#index)