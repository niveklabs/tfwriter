# fortios_systemautoupdate_pushupdate

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
module "fortios_systemautoupdate_pushupdate" {
  source = "./modules/fortios/r/fortios_systemautoupdate_pushupdate"

  # address - (required) is a type of string
  address = null
  # override - (required) is a type of string
  override = null
  # port - (required) is a type of number
  port = null
  # status - (required) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "override" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "status" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemautoupdate_pushupdate" "this" {
  # address - (required) is a type of string
  address = var.address
  # override - (required) is a type of string
  override = var.override
  # port - (required) is a type of number
  port = var.port
  # status - (required) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_systemautoupdate_pushupdate.this.id
}

output "this" {
  value = fortios_systemautoupdate_pushupdate.this
}
```

[top](#index)