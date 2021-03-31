# opc_compute_security_ip_list

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
module "opc_compute_security_ip_list" {
  source = "./modules/opc/r/opc_compute_security_ip_list"

  # description - (optional) is a type of string
  description = null
  # ip_entries - (required) is a type of list of string
  ip_entries = []
  # name - (required) is a type of string
  name = null
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

variable "ip_entries" {
  description = "(required)"
  type        = list(string)
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_security_ip_list" "this" {
  description = var.description
  ip_entries  = var.ip_entries
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_security_ip_list.this.id
}

output "this" {
  value = opc_compute_security_ip_list.this
}
```

[top](#index)