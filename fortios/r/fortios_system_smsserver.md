# fortios_system_smsserver

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
module "fortios_system_smsserver" {
  source = "./modules/fortios/r/fortios_system_smsserver"

  # mail_server - (required) is a type of string
  mail_server = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "mail_server" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_smsserver" "this" {
  mail_server = var.mail_server
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_smsserver.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_smsserver.this.name
}

output "this" {
  value = fortios_system_smsserver.this
}
```

[top](#index)