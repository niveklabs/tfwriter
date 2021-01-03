# opc_compute_ip_association

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
module "opc_compute_ip_association" {
  source = "./modules/opc/r/opc_compute_ip_association"

  # name - (optional) is a type of string
  name = null
  # parent_pool - (required) is a type of string
  parent_pool = null
  # vcable - (required) is a type of string
  vcable = null
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
  description = "(required)"
  type        = string
}

variable "vcable" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_ip_association" "this" {
  name        = var.name
  parent_pool = var.parent_pool
  vcable      = var.vcable
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ip_association.this.id
}

output "name" {
  description = "returns a string"
  value       = opc_compute_ip_association.this.name
}

output "this" {
  value = opc_compute_ip_association.this
}
```

[top](#index)