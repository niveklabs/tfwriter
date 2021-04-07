# aci_epg_to_static_path

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
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_epg_to_static_path" {
  source = "./modules/aci/r/aci_epg_to_static_path"

  # annotation - (optional) is a type of string
  annotation = null
  # application_epg_dn - (required) is a type of string
  application_epg_dn = null
  # description - (optional) is a type of string
  description = null
  # encap - (optional) is a type of string
  encap = null
  # instr_imedcy - (optional) is a type of string
  instr_imedcy = null
  # mode - (optional) is a type of string
  mode = null
  # primary_encap - (optional) is a type of string
  primary_encap = null
  # tdn - (required) is a type of string
  tdn = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_epg_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instr_imedcy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tdn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_epg_to_static_path" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # application_epg_dn - (required) is a type of string
  application_epg_dn = var.application_epg_dn
  # description - (optional) is a type of string
  description = var.description
  # encap - (optional) is a type of string
  encap = var.encap
  # instr_imedcy - (optional) is a type of string
  instr_imedcy = var.instr_imedcy
  # mode - (optional) is a type of string
  mode = var.mode
  # primary_encap - (optional) is a type of string
  primary_encap = var.primary_encap
  # tdn - (required) is a type of string
  tdn = var.tdn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_epg_to_static_path.this.description
}

output "encap" {
  description = "returns a string"
  value       = aci_epg_to_static_path.this.encap
}

output "id" {
  description = "returns a string"
  value       = aci_epg_to_static_path.this.id
}

output "instr_imedcy" {
  description = "returns a string"
  value       = aci_epg_to_static_path.this.instr_imedcy
}

output "mode" {
  description = "returns a string"
  value       = aci_epg_to_static_path.this.mode
}

output "primary_encap" {
  description = "returns a string"
  value       = aci_epg_to_static_path.this.primary_encap
}

output "this" {
  value = aci_epg_to_static_path.this
}
```

[top](#index)