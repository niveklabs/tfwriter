# aci_spine_port_selector

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
module "aci_spine_port_selector" {
  source = "./modules/aci/r/aci_spine_port_selector"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # spine_profile_dn - (required) is a type of string
  spine_profile_dn = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spine_profile_dn" {
  description = "(required)"
  type        = string
}

variable "tdn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_spine_port_selector" "this" {
  annotation       = var.annotation
  description      = var.description
  spine_profile_dn = var.spine_profile_dn
  tdn              = var.tdn
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_spine_port_selector.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_spine_port_selector.this.id
}

output "this" {
  value = aci_spine_port_selector.this
}
```

[top](#index)