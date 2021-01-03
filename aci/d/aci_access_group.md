# aci_access_group

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_access_group" {
  source = "./modules/aci/d/aci_access_group"

  # access_port_selector_dn - (required) is a type of string
  access_port_selector_dn = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # fex_id - (optional) is a type of string
  fex_id = null
  # tdn - (optional) is a type of string
  tdn = null
}
```

[top](#index)

### Variables

```terraform
variable "access_port_selector_dn" {
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

variable "fex_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tdn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_access_group" "this" {
  access_port_selector_dn = var.access_port_selector_dn
  annotation              = var.annotation
  description             = var.description
  fex_id                  = var.fex_id
  tdn                     = var.tdn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_access_group.this.description
}

output "fex_id" {
  description = "returns a string"
  value       = data.aci_access_group.this.fex_id
}

output "id" {
  description = "returns a string"
  value       = data.aci_access_group.this.id
}

output "tdn" {
  description = "returns a string"
  value       = data.aci_access_group.this.tdn
}

output "this" {
  value = aci_access_group.this
}
```

[top](#index)