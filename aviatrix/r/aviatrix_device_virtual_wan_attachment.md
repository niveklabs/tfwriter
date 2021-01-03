# aviatrix_device_virtual_wan_attachment

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
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_device_virtual_wan_attachment" {
  source = "./modules/aviatrix/r/aviatrix_device_virtual_wan_attachment"

  # account_name - (required) is a type of string
  account_name = null
  # connection_name - (required) is a type of string
  connection_name = null
  # device_bgp_asn - (required) is a type of number
  device_bgp_asn = null
  # device_name - (required) is a type of string
  device_name = null
  # hub_name - (required) is a type of string
  hub_name = null
  # resource_group - (required) is a type of string
  resource_group = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Azure access account name."
  type        = string
}

variable "connection_name" {
  description = "(required) - Connection name."
  type        = string
}

variable "device_bgp_asn" {
  description = "(required) - Device AS Number."
  type        = number
}

variable "device_name" {
  description = "(required) - Device name."
  type        = string
}

variable "hub_name" {
  description = "(required) - Virtual WAN vhub name."
  type        = string
}

variable "resource_group" {
  description = "(required) - ARM resource group name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_device_virtual_wan_attachment" "this" {
  account_name    = var.account_name
  connection_name = var.connection_name
  device_bgp_asn  = var.device_bgp_asn
  device_name     = var.device_name
  hub_name        = var.hub_name
  resource_group  = var.resource_group
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_device_virtual_wan_attachment.this.id
}

output "this" {
  value = aviatrix_device_virtual_wan_attachment.this
}
```

[top](#index)