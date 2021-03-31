# aviatrix_trans_peer

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_trans_peer" {
  source = null

  # nexthop - (required) is a type of string
  nexthop = null
  # reachable_cidr - (required) is a type of string
  reachable_cidr = null
  # source - (required) is a type of string
}
```

[top](#index)

### Variables

```terraform
variable "nexthop" {
  description = "(required) - Name of nexthop gateway."
  type        = string
}

variable "reachable_cidr" {
  description = "(required) - Destination CIDR."
  type        = string
}

variable "source" {
  description = "(required) - Name of Source gateway."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_trans_peer" "this" {
  nexthop        = var.nexthop
  reachable_cidr = var.reachable_cidr
  source         = var.source
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_trans_peer.this.id
}

output "this" {
  value = aviatrix_trans_peer.this
}
```

[top](#index)