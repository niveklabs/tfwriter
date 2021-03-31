# aviatrix_azure_spoke_native_peering

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
module "aviatrix_azure_spoke_native_peering" {
  source = "./modules/aviatrix/r/aviatrix_azure_spoke_native_peering"

  # spoke_account_name - (required) is a type of string
  spoke_account_name = null
  # spoke_region - (required) is a type of string
  spoke_region = null
  # spoke_vpc_id - (required) is a type of string
  spoke_vpc_id = null
  # transit_gateway_name - (required) is a type of string
  transit_gateway_name = null
}
```

[top](#index)

### Variables

```terraform
variable "spoke_account_name" {
  description = "(required) - An Aviatrix account that corresponds to a subscription in Azure."
  type        = string
}

variable "spoke_region" {
  description = "(required) - Spoke VNet region."
  type        = string
}

variable "spoke_vpc_id" {
  description = "(required) - Combination of the Spoke VNet name and resource group."
  type        = string
}

variable "transit_gateway_name" {
  description = "(required) - Name of an azure transit gateway with transit firenet enabled."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_azure_spoke_native_peering" "this" {
  spoke_account_name   = var.spoke_account_name
  spoke_region         = var.spoke_region
  spoke_vpc_id         = var.spoke_vpc_id
  transit_gateway_name = var.transit_gateway_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_azure_spoke_native_peering.this.id
}

output "this" {
  value = aviatrix_azure_spoke_native_peering.this
}
```

[top](#index)