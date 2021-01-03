# aci_fabric_if_pol

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
module "aci_fabric_if_pol" {
  source = "./modules/aci/r/aci_fabric_if_pol"

  # annotation - (optional) is a type of string
  annotation = null
  # auto_neg - (optional) is a type of string
  auto_neg = null
  # description - (optional) is a type of string
  description = null
  # fec_mode - (optional) is a type of string
  fec_mode = null
  # link_debounce - (optional) is a type of string
  link_debounce = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # speed - (optional) is a type of string
  speed = null
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

variable "auto_neg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fec_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_debounce" {
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

variable "speed" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_fabric_if_pol" "this" {
  annotation    = var.annotation
  auto_neg      = var.auto_neg
  description   = var.description
  fec_mode      = var.fec_mode
  link_debounce = var.link_debounce
  name          = var.name
  name_alias    = var.name_alias
  speed         = var.speed
}
```

[top](#index)

### Outputs

```terraform
output "auto_neg" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.auto_neg
}

output "description" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.description
}

output "fec_mode" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.fec_mode
}

output "id" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.id
}

output "link_debounce" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.link_debounce
}

output "name_alias" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.name_alias
}

output "speed" {
  description = "returns a string"
  value       = aci_fabric_if_pol.this.speed
}

output "this" {
  value = aci_fabric_if_pol.this
}
```

[top](#index)