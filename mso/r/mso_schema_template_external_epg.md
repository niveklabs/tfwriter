# mso_schema_template_external_epg

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "mso_schema_template_external_epg" {
  source = "./modules/mso/r/mso_schema_template_external_epg"

  # anp_name - (optional) is a type of string
  anp_name = null
  # anp_schema_id - (optional) is a type of string
  anp_schema_id = null
  # anp_template_name - (optional) is a type of string
  anp_template_name = null
  # display_name - (required) is a type of string
  display_name = null
  # external_epg_name - (required) is a type of string
  external_epg_name = null
  # external_epg_type - (optional) is a type of string
  external_epg_type = null
  # include_in_preferred_group - (optional) is a type of bool
  include_in_preferred_group = null
  # l3out_name - (optional) is a type of string
  l3out_name = null
  # l3out_schema_id - (optional) is a type of string
  l3out_schema_id = null
  # l3out_template_name - (optional) is a type of string
  l3out_template_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # selector_ip - (optional) is a type of string
  selector_ip = null
  # selector_name - (optional) is a type of string
  selector_name = null
  # site_id - (optional) is a type of list of string
  site_id = []
  # template_name - (required) is a type of string
  template_name = null
  # vrf_name - (required) is a type of string
  vrf_name = null
  # vrf_schema_id - (optional) is a type of string
  vrf_schema_id = null
  # vrf_template_name - (optional) is a type of string
  vrf_template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "anp_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anp_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anp_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "external_epg_name" {
  description = "(required)"
  type        = string
}

variable "external_epg_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_in_preferred_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "l3out_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "l3out_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "l3out_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "selector_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "site_id" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "vrf_name" {
  description = "(required)"
  type        = string
}

variable "vrf_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_external_epg" "this" {
  # anp_name - (optional) is a type of string
  anp_name = var.anp_name
  # anp_schema_id - (optional) is a type of string
  anp_schema_id = var.anp_schema_id
  # anp_template_name - (optional) is a type of string
  anp_template_name = var.anp_template_name
  # display_name - (required) is a type of string
  display_name = var.display_name
  # external_epg_name - (required) is a type of string
  external_epg_name = var.external_epg_name
  # external_epg_type - (optional) is a type of string
  external_epg_type = var.external_epg_type
  # include_in_preferred_group - (optional) is a type of bool
  include_in_preferred_group = var.include_in_preferred_group
  # l3out_name - (optional) is a type of string
  l3out_name = var.l3out_name
  # l3out_schema_id - (optional) is a type of string
  l3out_schema_id = var.l3out_schema_id
  # l3out_template_name - (optional) is a type of string
  l3out_template_name = var.l3out_template_name
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # selector_ip - (optional) is a type of string
  selector_ip = var.selector_ip
  # selector_name - (optional) is a type of string
  selector_name = var.selector_name
  # site_id - (optional) is a type of list of string
  site_id = var.site_id
  # template_name - (required) is a type of string
  template_name = var.template_name
  # vrf_name - (required) is a type of string
  vrf_name = var.vrf_name
  # vrf_schema_id - (optional) is a type of string
  vrf_schema_id = var.vrf_schema_id
  # vrf_template_name - (optional) is a type of string
  vrf_template_name = var.vrf_template_name
}
```

[top](#index)

### Outputs

```terraform
output "anp_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.anp_name
}

output "anp_schema_id" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.anp_schema_id
}

output "anp_template_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.anp_template_name
}

output "external_epg_type" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.external_epg_type
}

output "id" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.id
}

output "l3out_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.l3out_name
}

output "l3out_schema_id" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.l3out_schema_id
}

output "l3out_template_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.l3out_template_name
}

output "selector_ip" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.selector_ip
}

output "selector_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.selector_name
}

output "site_id" {
  description = "returns a list of string"
  value       = mso_schema_template_external_epg.this.site_id
}

output "vrf_schema_id" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.vrf_schema_id
}

output "vrf_template_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg.this.vrf_template_name
}

output "this" {
  value = mso_schema_template_external_epg.this
}
```

[top](#index)