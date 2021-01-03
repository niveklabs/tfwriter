# fortios_firewall_object_vipgroup

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_object_vipgroup" {
  source = "./modules/fortios/r/fortios_firewall_object_vipgroup"

  # comments - (optional) is a type of string
  comments = null
  # interface - (optional) is a type of string
  interface = null
  # member - (required) is a type of list of string
  member = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member" {
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
resource "fortios_firewall_object_vipgroup" "this" {
  comments  = var.comments
  interface = var.interface
  member    = var.member
  name      = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_vipgroup.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_firewall_object_vipgroup.this.interface
}

output "this" {
  value = fortios_firewall_object_vipgroup.this
}
```

[top](#index)