# mso_schema_site_anp_epg_static_port

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_site_anp_epg_static_port" {
  source = "./modules/mso/d/mso_schema_site_anp_epg_static_port"

  # anp_name - (required) is a type of string
  anp_name = null
  # deployment_immediacy - (optional) is a type of string
  deployment_immediacy = null
  # epg_name - (required) is a type of string
  epg_name = null
  # fex - (optional) is a type of string
  fex = null
  # leaf - (required) is a type of string
  leaf = null
  # micro_seg_vlan - (optional) is a type of number
  micro_seg_vlan = null
  # mode - (optional) is a type of string
  mode = null
  # path - (required) is a type of string
  path = null
  # path_type - (required) is a type of string
  path_type = null
  # pod - (required) is a type of string
  pod = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
  # vlan - (optional) is a type of number
  vlan = null
}
```

[top](#index)

### Variables

```terraform
variable "anp_name" {
  description = "(required)"
  type        = string
}

variable "deployment_immediacy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "epg_name" {
  description = "(required)"
  type        = string
}

variable "fex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "leaf" {
  description = "(required)"
  type        = string
}

variable "micro_seg_vlan" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "path_type" {
  description = "(required)"
  type        = string
}

variable "pod" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "site_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "vlan" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_site_anp_epg_static_port" "this" {
  # anp_name - (required) is a type of string
  anp_name = var.anp_name
  # deployment_immediacy - (optional) is a type of string
  deployment_immediacy = var.deployment_immediacy
  # epg_name - (required) is a type of string
  epg_name = var.epg_name
  # fex - (optional) is a type of string
  fex = var.fex
  # leaf - (required) is a type of string
  leaf = var.leaf
  # micro_seg_vlan - (optional) is a type of number
  micro_seg_vlan = var.micro_seg_vlan
  # mode - (optional) is a type of string
  mode = var.mode
  # path - (required) is a type of string
  path = var.path
  # path_type - (required) is a type of string
  path_type = var.path_type
  # pod - (required) is a type of string
  pod = var.pod
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # site_id - (required) is a type of string
  site_id = var.site_id
  # template_name - (required) is a type of string
  template_name = var.template_name
  # vlan - (optional) is a type of number
  vlan = var.vlan
}
```

[top](#index)

### Outputs

```terraform
output "deployment_immediacy" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_static_port.this.deployment_immediacy
}

output "fex" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_static_port.this.fex
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_static_port.this.id
}

output "micro_seg_vlan" {
  description = "returns a number"
  value       = data.mso_schema_site_anp_epg_static_port.this.micro_seg_vlan
}

output "mode" {
  description = "returns a string"
  value       = data.mso_schema_site_anp_epg_static_port.this.mode
}

output "vlan" {
  description = "returns a number"
  value       = data.mso_schema_site_anp_epg_static_port.this.vlan
}

output "this" {
  value = mso_schema_site_anp_epg_static_port.this
}
```

[top](#index)