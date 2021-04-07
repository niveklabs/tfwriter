# opc_compute_security_application

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
module "opc_compute_security_application" {
  source = "./modules/opc/r/opc_compute_security_application"

  # description - (optional) is a type of string
  description = null
  # dport - (optional) is a type of string
  dport = null
  # icmpcode - (optional) is a type of string
  icmpcode = null
  # icmptype - (optional) is a type of string
  icmptype = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
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

variable "dport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmpcode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmptype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_security_application" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dport - (optional) is a type of string
  dport = var.dport
  # icmpcode - (optional) is a type of string
  icmpcode = var.icmpcode
  # icmptype - (optional) is a type of string
  icmptype = var.icmptype
  # name - (required) is a type of string
  name = var.name
  # protocol - (required) is a type of string
  protocol = var.protocol
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_security_application.this.id
}

output "this" {
  value = opc_compute_security_application.this
}
```

[top](#index)