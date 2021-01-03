# ad_gplink

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_gplink" {
  source = "./modules/ad/r/ad_gplink"

  # enabled - (optional) is a type of bool
  enabled = null
  # enforced - (optional) is a type of bool
  enforced = null
  # gpo_guid - (required) is a type of string
  gpo_guid = null
  # order - (optional) is a type of number
  order = null
  # target_dn - (required) is a type of string
  target_dn = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Controls the state of the GP link between a GPO and a container object."
  type        = bool
  default     = null
}

variable "enforced" {
  description = "(optional) - If set to true, the GPO will be enforced on the container object."
  type        = bool
  default     = null
}

variable "gpo_guid" {
  description = "(required) - The GUID of the GPO that will be linked to the container object."
  type        = string
}

variable "order" {
  description = "(optional) - Sets the precedence between multiple GPOs linked to the same container object."
  type        = number
  default     = null
}

variable "target_dn" {
  description = "(required) - The DN of the object the GPO will be linked to."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ad_gplink" "this" {
  enabled   = var.enabled
  enforced  = var.enforced
  gpo_guid  = var.gpo_guid
  order     = var.order
  target_dn = var.target_dn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ad_gplink.this.id
}

output "this" {
  value = ad_gplink.this
}
```

[top](#index)