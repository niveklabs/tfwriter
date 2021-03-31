# fortios_firewall_ippool6

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
module "fortios_firewall_ippool6" {
  source = "./modules/fortios/r/fortios_firewall_ippool6"

  # comments - (optional) is a type of string
  comments = null
  # endip - (required) is a type of string
  endip = null
  # name - (optional) is a type of string
  name = null
  # startip - (required) is a type of string
  startip = null
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

variable "endip" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "startip" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_ippool6" "this" {
  comments = var.comments
  endip    = var.endip
  name     = var.name
  startip  = var.startip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_ippool6.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_ippool6.this.name
}

output "this" {
  value = fortios_firewall_ippool6.this
}
```

[top](#index)