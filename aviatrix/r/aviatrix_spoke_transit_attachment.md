# aviatrix_spoke_transit_attachment

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
module "aviatrix_spoke_transit_attachment" {
  source = "./modules/aviatrix/r/aviatrix_spoke_transit_attachment"

  # route_tables - (optional) is a type of set of string
  route_tables = []
  # spoke_gw_name - (required) is a type of string
  spoke_gw_name = null
  # transit_gw_name - (required) is a type of string
  transit_gw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "route_tables" {
  description = "(optional) - Learned routes will be propagated to these route tables."
  type        = set(string)
  default     = null
}

variable "spoke_gw_name" {
  description = "(required) - Name of the spoke gateway to attach to transit network."
  type        = string
}

variable "transit_gw_name" {
  description = "(required) - Name of the transit gateway to attach the spoke gateway to."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_spoke_transit_attachment" "this" {
  route_tables    = var.route_tables
  spoke_gw_name   = var.spoke_gw_name
  transit_gw_name = var.transit_gw_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_spoke_transit_attachment.this.id
}

output "this" {
  value = aviatrix_spoke_transit_attachment.this
}
```

[top](#index)