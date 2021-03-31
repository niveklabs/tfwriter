# fortios_firewall_object_addressgroup

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_object_addressgroup" {
  source = "./modules/fortios/r/fortios_firewall_object_addressgroup"

  # comment - (optional) is a type of string
  comment = null
  # member - (required) is a type of list of string
  member = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
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
resource "fortios_firewall_object_addressgroup" "this" {
  comment = var.comment
  member  = var.member
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_addressgroup.this.id
}

output "this" {
  value = fortios_firewall_object_addressgroup.this
}
```

[top](#index)