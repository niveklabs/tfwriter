# opc_compute_security_list

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
module "opc_compute_security_list" {
  source = "./modules/opc/r/opc_compute_security_list"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # outbound_cidr_policy - (optional) is a type of string
  outbound_cidr_policy = null
  # policy - (optional) is a type of string
  policy = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "outbound_cidr_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_security_list" "this" {
  description          = var.description
  name                 = var.name
  outbound_cidr_policy = var.outbound_cidr_policy
  policy               = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_security_list.this.id
}

output "this" {
  value = opc_compute_security_list.this
}
```

[top](#index)