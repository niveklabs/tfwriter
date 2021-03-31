# fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype

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
module "fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype"

  # auth_type - (optional) is a type of string
  auth_type = null
  # name - (optional) is a type of string
  name = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype" "this" {
  auth_type = var.auth_type
  name      = var.name
  url       = var.url
}
```

[top](#index)

### Outputs

```terraform
output "auth_type" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype.this.auth_type
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype.this.name
}

output "url" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype.this.url
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_anqpnetworkauthtype.this
}
```

[top](#index)