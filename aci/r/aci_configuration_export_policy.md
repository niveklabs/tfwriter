# aci_configuration_export_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_configuration_export_policy" {
  source = "./modules/aci/r/aci_configuration_export_policy"

  # admin_st - (optional) is a type of string
  admin_st = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # format - (optional) is a type of string
  format = null
  # include_secure_fields - (optional) is a type of string
  include_secure_fields = null
  # max_snapshot_count - (optional) is a type of string
  max_snapshot_count = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_config_rs_export_destination - (optional) is a type of string
  relation_config_rs_export_destination = null
  # relation_config_rs_export_scheduler - (optional) is a type of string
  relation_config_rs_export_scheduler = null
  # relation_config_rs_remote_path - (optional) is a type of string
  relation_config_rs_remote_path = null
  # relation_trig_rs_triggerable - (optional) is a type of string
  relation_trig_rs_triggerable = null
  # snapshot - (optional) is a type of string
  snapshot = null
  # target_dn - (optional) is a type of string
  target_dn = null
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

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_secure_fields" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_snapshot_count" {
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

variable "relation_config_rs_export_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_config_rs_export_scheduler" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_config_rs_remote_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_trig_rs_triggerable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_dn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_configuration_export_policy" "this" {
  admin_st                              = var.admin_st
  annotation                            = var.annotation
  description                           = var.description
  format                                = var.format
  include_secure_fields                 = var.include_secure_fields
  max_snapshot_count                    = var.max_snapshot_count
  name                                  = var.name
  name_alias                            = var.name_alias
  relation_config_rs_export_destination = var.relation_config_rs_export_destination
  relation_config_rs_export_scheduler   = var.relation_config_rs_export_scheduler
  relation_config_rs_remote_path        = var.relation_config_rs_remote_path
  relation_trig_rs_triggerable          = var.relation_trig_rs_triggerable
  snapshot                              = var.snapshot
  target_dn                             = var.target_dn
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.description
}

output "format" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.format
}

output "id" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.id
}

output "include_secure_fields" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.include_secure_fields
}

output "max_snapshot_count" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.max_snapshot_count
}

output "name_alias" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.name_alias
}

output "snapshot" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.snapshot
}

output "target_dn" {
  description = "returns a string"
  value       = aci_configuration_export_policy.this.target_dn
}

output "this" {
  value = aci_configuration_export_policy.this
}
```

[top](#index)