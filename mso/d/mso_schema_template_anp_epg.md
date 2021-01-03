# mso_schema_template_anp_epg

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
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_anp_epg" {
  source = "./modules/mso/d/mso_schema_template_anp_epg"

  # anp_name - (required) is a type of string
  anp_name = null
  # bd_name - (optional) is a type of string
  bd_name = null
  # bd_schema_id - (optional) is a type of string
  bd_schema_id = null
  # bd_template_name - (optional) is a type of string
  bd_template_name = null
  # display_name - (optional) is a type of string
  display_name = null
  # intersite_multicast_source - (optional) is a type of bool
  intersite_multicast_source = null
  # intra_epg - (optional) is a type of string
  intra_epg = null
  # name - (required) is a type of string
  name = null
  # preferred_group - (optional) is a type of bool
  preferred_group = null
  # proxy_arp - (optional) is a type of bool
  proxy_arp = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null
  # useg_epg - (optional) is a type of bool
  useg_epg = null
  # vrf_name - (optional) is a type of string
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
  description = "(required)"
  type        = string
}

variable "bd_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bd_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bd_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intersite_multicast_source" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "intra_epg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "preferred_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "proxy_arp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "useg_epg" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vrf_name" {
  description = "(optional)"
  type        = string
  default     = null
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

### Datasource

```terraform
data "mso_schema_template_anp_epg" "this" {
  anp_name                   = var.anp_name
  bd_name                    = var.bd_name
  bd_schema_id               = var.bd_schema_id
  bd_template_name           = var.bd_template_name
  display_name               = var.display_name
  intersite_multicast_source = var.intersite_multicast_source
  intra_epg                  = var.intra_epg
  name                       = var.name
  preferred_group            = var.preferred_group
  proxy_arp                  = var.proxy_arp
  schema_id                  = var.schema_id
  template_name              = var.template_name
  useg_epg                   = var.useg_epg
  vrf_name                   = var.vrf_name
  vrf_schema_id              = var.vrf_schema_id
  vrf_template_name          = var.vrf_template_name
}
```

[top](#index)

### Outputs

```terraform
output "bd_name" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.bd_name
}

output "bd_schema_id" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.bd_schema_id
}

output "bd_template_name" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.bd_template_name
}

output "display_name" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.id
}

output "intersite_multicast_source" {
  description = "returns a bool"
  value       = data.mso_schema_template_anp_epg.this.intersite_multicast_source
}

output "intra_epg" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.intra_epg
}

output "preferred_group" {
  description = "returns a bool"
  value       = data.mso_schema_template_anp_epg.this.preferred_group
}

output "proxy_arp" {
  description = "returns a bool"
  value       = data.mso_schema_template_anp_epg.this.proxy_arp
}

output "useg_epg" {
  description = "returns a bool"
  value       = data.mso_schema_template_anp_epg.this.useg_epg
}

output "vrf_name" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.vrf_name
}

output "vrf_schema_id" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.vrf_schema_id
}

output "vrf_template_name" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg.this.vrf_template_name
}

output "this" {
  value = mso_schema_template_anp_epg.this
}
```

[top](#index)