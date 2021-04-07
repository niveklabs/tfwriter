# aci_epgs_using_function

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
module "aci_epgs_using_function" {
  source = "./modules/aci/d/aci_epgs_using_function"

  # access_generic_dn - (required) is a type of string
  access_generic_dn = null
  # annotation - (optional) is a type of string
  annotation = null
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
variable "access_generic_dn" {
  description = "(required)"
  type        = string
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

### Datasource

```terraform
data "aci_epgs_using_function" "this" {
  # access_generic_dn - (required) is a type of string
  access_generic_dn = var.access_generic_dn
  # annotation - (optional) is a type of string
  annotation = var.annotation
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
  value       = data.aci_epgs_using_function.this.description
}

output "encap" {
  description = "returns a string"
  value       = data.aci_epgs_using_function.this.encap
}

output "id" {
  description = "returns a string"
  value       = data.aci_epgs_using_function.this.id
}

output "instr_imedcy" {
  description = "returns a string"
  value       = data.aci_epgs_using_function.this.instr_imedcy
}

output "mode" {
  description = "returns a string"
  value       = data.aci_epgs_using_function.this.mode
}

output "primary_encap" {
  description = "returns a string"
  value       = data.aci_epgs_using_function.this.primary_encap
}

output "this" {
  value = aci_epgs_using_function.this
}
```

[top](#index)