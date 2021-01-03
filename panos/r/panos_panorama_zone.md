# panos_panorama_zone

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
module "panos_panorama_zone" {
  source = "./modules/panos/r/panos_panorama_zone"

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
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
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
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_acls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "include_acls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "interfaces" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "log_setting" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_profile" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_zone" "this" {
  enable_user_id = var.enable_user_id
  exclude_acls   = var.exclude_acls
  include_acls   = var.include_acls
  interfaces     = var.interfaces
  log_setting    = var.log_setting
  mode           = var.mode
  name           = var.name
  template       = var.template
  template_stack = var.template_stack
  vsys           = var.vsys
  zone_profile   = var.zone_profile
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_zone.this.id
}

output "interfaces" {
  description = "returns a list of string"
  value       = panos_panorama_zone.this.interfaces
}

output "this" {
  value = panos_panorama_zone.this
}
```

[top](#index)