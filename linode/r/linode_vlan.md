# linode_vlan

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_vlan" {
  source = "./modules/linode/r/linode_vlan"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # linodes - (optional) is a type of set of number
  linodes = []
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the vlan for display purposes only."
  type        = string
  default     = null
}

variable "linodes" {
  description = "(optional) - The IDs of the Linodes to attach to this vlan."
  type        = set(number)
  default     = null
}

variable "region" {
  description = "(required) - The region where the vlan is deployed."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "linode_vlan" "this" {
  cidr_block  = var.cidr_block
  description = var.description
  linodes     = var.linodes
  region      = var.region
}
```

[top](#index)

### Outputs

```terraform
output "attached_linodes" {
  description = "returns a list of object"
  value       = linode_vlan.this.attached_linodes
}

output "id" {
  description = "returns a string"
  value       = linode_vlan.this.id
}

output "this" {
  value = linode_vlan.this
}
```

[top](#index)