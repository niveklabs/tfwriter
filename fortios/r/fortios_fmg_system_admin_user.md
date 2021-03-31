# fortios_fmg_system_admin_user

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
module "fortios_fmg_system_admin_user" {
  source = "./modules/fortios/r/fortios_fmg_system_admin_user"

  # description - (optional) is a type of string
  description = null
  # password - (optional) is a type of string
  password = null
  # profileid - (optional) is a type of string
  profileid = null
  # radius_server - (optional) is a type of string
  radius_server = null
  # rpc_permit - (optional) is a type of string
  rpc_permit = null
  # trusthost1 - (optional) is a type of string
  trusthost1 = null
  # trusthost2 - (optional) is a type of string
  trusthost2 = null
  # trusthost3 - (optional) is a type of string
  trusthost3 = null
  # user_type - (optional) is a type of string
  user_type = null
  # userid - (required) is a type of string
  userid = null
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

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profileid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rpc_permit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "userid" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_admin_user" "this" {
  description   = var.description
  password      = var.password
  profileid     = var.profileid
  radius_server = var.radius_server
  rpc_permit    = var.rpc_permit
  trusthost1    = var.trusthost1
  trusthost2    = var.trusthost2
  trusthost3    = var.trusthost3
  user_type     = var.user_type
  userid        = var.userid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_admin_user.this.id
}

output "this" {
  value = fortios_fmg_system_admin_user.this
}
```

[top](#index)