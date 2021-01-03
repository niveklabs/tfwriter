# aviatrix_transit_vpc

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
module "aviatrix_transit_vpc" {
  source = "./modules/aviatrix/r/aviatrix_transit_vpc"

  # account_name - (required) is a type of string
  account_name = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # connected_transit - (optional) is a type of string
  connected_transit = null
  # enable_firenet_interfaces - (optional) is a type of bool
  enable_firenet_interfaces = null
  # enable_hybrid_connection - (optional) is a type of bool
  enable_hybrid_connection = null
  # enable_nat - (optional) is a type of string
  enable_nat = null
  # gw_name - (required) is a type of string
  gw_name = null
  # ha_gw_size - (optional) is a type of string
  ha_gw_size = null
  # ha_insane_mode_az - (optional) is a type of string
  ha_insane_mode_az = null
  # ha_subnet - (optional) is a type of string
  ha_subnet = null
  # insane_mode - (optional) is a type of bool
  insane_mode = null
  # insane_mode_az - (optional) is a type of string
  insane_mode_az = null
  # subnet - (required) is a type of string
  subnet = null
  # tag_list - (optional) is a type of list of string
  tag_list = []
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vpc_reg - (required) is a type of string
  vpc_reg = null
  # vpc_size - (required) is a type of string
  vpc_size = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
}

variable "cloud_type" {
  description = "(required) - Type of cloud service provider, requires an integer value. Use 1 for AWS."
  type        = number
}

variable "connected_transit" {
  description = "(optional) - Specify Connected Transit status."
  type        = string
  default     = null
}

variable "enable_firenet_interfaces" {
  description = "(optional) - Specify whether to enable firenet interfaces or not."
  type        = bool
  default     = null
}

variable "enable_hybrid_connection" {
  description = "(optional) - Sign of readiness for TGW connection."
  type        = bool
  default     = null
}

variable "enable_nat" {
  description = "(optional) - Enable NAT for this container."
  type        = string
  default     = null
}

variable "gw_name" {
  description = "(required) - Name of the gateway which is going to be created."
  type        = string
}

variable "ha_gw_size" {
  description = "(optional) - HA Gateway Size. Mandatory if HA is enabled (ha_subnet is set)."
  type        = string
  default     = null
}

variable "ha_insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Transit HA Gateway. Required if insane_mode is enabled and ha_subnet is set."
  type        = string
  default     = null
}

variable "ha_subnet" {
  description = "(optional) - HA Subnet."
  type        = string
  default     = null
}

variable "insane_mode" {
  description = "(optional) - Enable Insane Mode for Transit. Valid values: true, false. If insane mode is enabled, gateway size has to at least be c5 size."
  type        = bool
  default     = null
}

variable "insane_mode_az" {
  description = "(optional) - AZ of subnet being created for Insane Mode Transit Gateway. Required if insane_mode is enabled."
  type        = string
  default     = null
}

variable "subnet" {
  description = "(required) - Public Subnet Name."
  type        = string
}

variable "tag_list" {
  description = "(optional) - Instance tag of cloud provider."
  type        = list(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - VPC-ID/VNet-Name of cloud provider."
  type        = string
}

variable "vpc_reg" {
  description = "(required) - Region of cloud provider."
  type        = string
}

variable "vpc_size" {
  description = "(required) - Size of the gateway instance."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_transit_vpc" "this" {
  account_name              = var.account_name
  cloud_type                = var.cloud_type
  connected_transit         = var.connected_transit
  enable_firenet_interfaces = var.enable_firenet_interfaces
  enable_hybrid_connection  = var.enable_hybrid_connection
  enable_nat                = var.enable_nat
  gw_name                   = var.gw_name
  ha_gw_size                = var.ha_gw_size
  ha_insane_mode_az         = var.ha_insane_mode_az
  ha_subnet                 = var.ha_subnet
  insane_mode               = var.insane_mode
  insane_mode_az            = var.insane_mode_az
  subnet                    = var.subnet
  tag_list                  = var.tag_list
  vpc_id                    = var.vpc_id
  vpc_reg                   = var.vpc_reg
  vpc_size                  = var.vpc_size
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_transit_vpc.this.id
}

output "this" {
  value = aviatrix_transit_vpc.this
}
```

[top](#index)