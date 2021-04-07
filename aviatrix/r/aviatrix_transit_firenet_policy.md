# aviatrix_transit_firenet_policy

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
module "aviatrix_transit_firenet_policy" {
  source = "./modules/aviatrix/r/aviatrix_transit_firenet_policy"

  # inspected_resource_name - (required) is a type of string
  inspected_resource_name = null
  # transit_firenet_gateway_name - (required) is a type of string
  transit_firenet_gateway_name = null
}
```

[top](#index)

### Variables

```terraform
variable "inspected_resource_name" {
  description = "(required) - Name of the resource to be added to transit firenet policy."
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
resource "aviatrix_transit_firenet_policy" "this" {
  # inspected_resource_name - (required) is a type of string
  inspected_resource_name = var.inspected_resource_name
  # transit_firenet_gateway_name - (required) is a type of string
  transit_firenet_gateway_name = var.transit_firenet_gateway_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_transit_firenet_policy.this.id
}

output "this" {
  value = aviatrix_transit_firenet_policy.this
}
```

[top](#index)