# fortios_switchcontroller_switchprofile

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
module "fortios_switchcontroller_switchprofile" {
  source = "./modules/fortios/r/fortios_switchcontroller_switchprofile"

  # login_passwd - (optional) is a type of string
  login_passwd = null
  # login_passwd_override - (optional) is a type of string
  login_passwd_override = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "login_passwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_passwd_override" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "fortios_switchcontroller_switchprofile" "this" {
  login_passwd          = var.login_passwd
  login_passwd_override = var.login_passwd_override
  name                  = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchprofile.this.id
}

output "login_passwd_override" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchprofile.this.login_passwd_override
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchprofile.this.name
}

output "this" {
  value = fortios_switchcontroller_switchprofile.this
}
```

[top](#index)