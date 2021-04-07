# aci_maintenance_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_maintenance_policy" {
  source = "./modules/aci/d/aci_maintenance_policy"

  # admin_st - (optional) is a type of string
  admin_st = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # graceful - (optional) is a type of string
  graceful = null
  # ignore_compat - (optional) is a type of string
  ignore_compat = null
  # internal_label - (optional) is a type of string
  internal_label = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # notif_cond - (optional) is a type of string
  notif_cond = null
  # run_mode - (optional) is a type of string
  run_mode = null
  # version - (optional) is a type of string
  version = null
  # version_check_override - (optional) is a type of string
  version_check_override = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_st" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graceful" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_compat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internal_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notif_cond" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "run_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_check_override" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_maintenance_policy" "this" {
  # admin_st - (optional) is a type of string
  admin_st = var.admin_st
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # graceful - (optional) is a type of string
  graceful = var.graceful
  # ignore_compat - (optional) is a type of string
  ignore_compat = var.ignore_compat
  # internal_label - (optional) is a type of string
  internal_label = var.internal_label
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # notif_cond - (optional) is a type of string
  notif_cond = var.notif_cond
  # run_mode - (optional) is a type of string
  run_mode = var.run_mode
  # version - (optional) is a type of string
  version = var.version
  # version_check_override - (optional) is a type of string
  version_check_override = var.version_check_override
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.description
}

output "graceful" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.graceful
}

output "id" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.id
}

output "ignore_compat" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.ignore_compat
}

output "internal_label" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.internal_label
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.name_alias
}

output "notif_cond" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.notif_cond
}

output "run_mode" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.run_mode
}

output "version" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.version
}

output "version_check_override" {
  description = "returns a string"
  value       = data.aci_maintenance_policy.this.version_check_override
}

output "this" {
  value = aci_maintenance_policy.this
}
```

[top](#index)