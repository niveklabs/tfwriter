# aviatrix_tunnel

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
module "aviatrix_tunnel" {
  source = "./modules/aviatrix/r/aviatrix_tunnel"

  # enable_ha - (optional) is a type of bool
  enable_ha = null
  # gw_name1 - (required) is a type of string
  gw_name1 = null
  # gw_name2 - (required) is a type of string
  gw_name2 = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_ha" {
  description = "(optional) - Whether Peering HA is enabled. Valid inputs: true or false."
  type        = bool
  default     = null
}

variable "gw_name1" {
  description = "(required) - The first VPC Container name to make a peer pair."
  type        = string
}

variable "gw_name2" {
  description = "(required) - The second VPC Container name to make a peer pair."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_tunnel" "this" {
  enable_ha = var.enable_ha
  gw_name1  = var.gw_name1
  gw_name2  = var.gw_name2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_tunnel.this.id
}

output "peering_hastatus" {
  description = "returns a string"
  value       = aviatrix_tunnel.this.peering_hastatus
}

output "peering_link" {
  description = "returns a string"
  value       = aviatrix_tunnel.this.peering_link
}

output "peering_state" {
  description = "returns a string"
  value       = aviatrix_tunnel.this.peering_state
}

output "this" {
  value = aviatrix_tunnel.this
}
```

[top](#index)