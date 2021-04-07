# opc_compute_security_association

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
module "opc_compute_security_association" {
  source = "./modules/opc/r/opc_compute_security_association"

  # name - (optional) is a type of string
  name = null
  # seclist - (required) is a type of string
  seclist = null
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

variable "seclist" {
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
resource "opc_compute_security_association" "this" {
  # name - (optional) is a type of string
  name = var.name
  # seclist - (required) is a type of string
  seclist = var.seclist
  # vcable - (required) is a type of string
  vcable = var.vcable
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_security_association.this.id
}

output "name" {
  description = "returns a string"
  value       = opc_compute_security_association.this.name
}

output "this" {
  value = opc_compute_security_association.this
}
```

[top](#index)