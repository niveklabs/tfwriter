# panos_zone

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_zone" {
  source = "./modules/panos/r/panos_zone"

  # enable_user_id - (optional) is a type of bool
  enable_user_id = null
  # exclude_acls - (optional) is a type of list of string
  exclude_acls = []
  # include_acls - (optional) is a type of list of string
  include_acls = []
  # interfaces - (optional) is a type of list of string
  interfaces = []
  # log_setting - (optional) is a type of string
  log_setting = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
  # zone_profile - (optional) is a type of string
  zone_profile = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_user_id" {
  description = "(optional) - The zone's mode"
  type        = bool
  default     = null
}

variable "exclude_acls" {
  description = "(optional) - User Identification exclude ACL list"
  type        = list(string)
  default     = null
}

variable "include_acls" {
  description = "(optional) - User Identification include ACL list"
  type        = list(string)
  default     = null
}

variable "interfaces" {
  description = "(optional) - User Identification include ACL list"
  type        = list(string)
  default     = null
}

variable "log_setting" {
  description = "(optional) - The zone's mode"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional) - The zone's mode"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The zone's name"
  type        = string
}

variable "vsys" {
  description = "(optional) - The vsys to put this zone in"
  type        = string
  default     = null
}

variable "zone_profile" {
  description = "(optional) - The zone's mode"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_zone" "this" {
  enable_user_id = var.enable_user_id
  exclude_acls   = var.exclude_acls
  include_acls   = var.include_acls
  interfaces     = var.interfaces
  log_setting    = var.log_setting
  mode           = var.mode
  name           = var.name
  vsys           = var.vsys
  zone_profile   = var.zone_profile
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_zone.this.id
}

output "interfaces" {
  description = "returns a list of string"
  value       = panos_zone.this.interfaces
}

output "this" {
  value = panos_zone.this
}
```

[top](#index)