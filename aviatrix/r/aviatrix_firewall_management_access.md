# aviatrix_firewall_management_access

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
module "aviatrix_firewall_management_access" {
  source = "./modules/aviatrix/r/aviatrix_firewall_management_access"

  # management_access_resource_name - (required) is a type of string
  management_access_resource_name = null
  # transit_firenet_gateway_name - (required) is a type of string
  transit_firenet_gateway_name = null
}
```

[top](#index)

### Variables

```terraform
variable "management_access_resource_name" {
  description = "(required) - Name of the resource to be enabled firewall management access."
  type        = string
}

variable "transit_firenet_gateway_name" {
  description = "(required) - Name of the transit firenet gateway."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firewall_management_access" "this" {
  # management_access_resource_name - (required) is a type of string
  management_access_resource_name = var.management_access_resource_name
  # transit_firenet_gateway_name - (required) is a type of string
  transit_firenet_gateway_name = var.transit_firenet_gateway_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_firewall_management_access.this.id
}

output "this" {
  value = aviatrix_firewall_management_access.this
}
```

[top](#index)