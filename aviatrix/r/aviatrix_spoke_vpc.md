# aviatrix_spoke_vpc

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
module "aviatrix_spoke_vpc" {
  source = "./modules/aviatrix/r/aviatrix_spoke_vpc"

  # account_name - (required) is a type of string
  account_name = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # enable_nat - (optional) is a type of string
  enable_nat = null
  # gw_name - (required) is a type of string
  gw_name = null
  # ha_gw_size - (optional) is a type of string
  ha_gw_size = null
  # ha_subnet - (optional) is a type of string
  ha_subnet = null
  # ha_zone - (optional) is a type of string
  ha_zone = null
  # single_az_ha - (optional) is a type of string
  single_az_ha = null
  # subnet - (required) is a type of string
  subnet = null
  # tag_list - (optional) is a type of list of string
  tag_list = []
  # transit_gw - (optional) is a type of string
  transit_gw = null
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
  description = "(required) - Type of cloud service provider."
  type        = number
}

variable "enable_nat" {
  description = "(optional) - Specify whether enabling NAT feature on the gateway or not."
  type        = string
  default     = null
}

variable "gw_name" {
  description = "(required) - Name of the gateway which is going to be created."
  type        = string
}

variable "ha_gw_size" {
  description = "(optional) - HA Gateway Size."
  type        = string
  default     = null
}

variable "ha_subnet" {
  description = "(optional) - HA Subnet. Required if enabling HA for AWS/AZURE."
  type        = string
  default     = null
}

variable "ha_zone" {
  description = "(optional) - HA Zone. Required if enabling HA for GCP."
  type        = string
  default     = null
}

variable "single_az_ha" {
  description = "(optional) - Set to 'enabled' if this feature is desired."
  type        = string
  default     = null
}

variable "subnet" {
  description = "(required) - Public Subnet Info."
  type        = string
}

variable "tag_list" {
  description = "(optional) - Instance tag of cloud provider."
  type        = list(string)
  default     = null
}

variable "transit_gw" {
  description = "(optional) - Specify the transit Gateway."
  type        = string
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
resource "aviatrix_spoke_vpc" "this" {
  account_name = var.account_name
  cloud_type   = var.cloud_type
  enable_nat   = var.enable_nat
  gw_name      = var.gw_name
  ha_gw_size   = var.ha_gw_size
  ha_subnet    = var.ha_subnet
  ha_zone      = var.ha_zone
  single_az_ha = var.single_az_ha
  subnet       = var.subnet
  tag_list     = var.tag_list
  transit_gw   = var.transit_gw
  vpc_id       = var.vpc_id
  vpc_reg      = var.vpc_reg
  vpc_size     = var.vpc_size
}
```

[top](#index)

### Outputs

```terraform
output "cloud_instance_id" {
  description = "returns a string"
  value       = aviatrix_spoke_vpc.this.cloud_instance_id
}

output "id" {
  description = "returns a string"
  value       = aviatrix_spoke_vpc.this.id
}

output "this" {
  value = aviatrix_spoke_vpc.this
}
```

[top](#index)