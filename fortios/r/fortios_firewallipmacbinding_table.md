# fortios_firewallipmacbinding_table

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
module "fortios_firewallipmacbinding_table" {
  source = "./modules/fortios/r/fortios_firewallipmacbinding_table"

  # ip - (required) is a type of string
  ip = null
  # mac - (optional) is a type of string
  mac = null
  # name - (optional) is a type of string
  name = null
  # seq_num - (optional) is a type of number
  seq_num = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required)"
  type        = string
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "seq_num" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallipmacbinding_table" "this" {
  # ip - (required) is a type of string
  ip = var.ip
  # mac - (optional) is a type of string
  mac = var.mac
  # name - (optional) is a type of string
  name = var.name
  # seq_num - (optional) is a type of number
  seq_num = var.seq_num
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_table.this.id
}

output "mac" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_table.this.mac
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_table.this.name
}

output "seq_num" {
  description = "returns a number"
  value       = fortios_firewallipmacbinding_table.this.seq_num
}

output "status" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_table.this.status
}

output "this" {
  value = fortios_firewallipmacbinding_table.this
}
```

[top](#index)