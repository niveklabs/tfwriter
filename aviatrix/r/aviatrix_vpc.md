# aviatrix_vpc

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
module "aviatrix_vpc" {
  source = "./modules/aviatrix/r/aviatrix_vpc"

  # account_name - (required) is a type of string
  account_name = null
  # aviatrix_firenet_vpc - (optional) is a type of bool
  aviatrix_firenet_vpc = null
  # aviatrix_transit_vpc - (optional) is a type of bool
  aviatrix_transit_vpc = null
  # cidr - (optional) is a type of string
  cidr = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # enable_native_gwlb - (optional) is a type of bool
  enable_native_gwlb = null
  # enable_private_oob_subnet - (optional) is a type of bool
  enable_private_oob_subnet = null
  # name - (required) is a type of string
  name = null
  # num_of_subnet_pairs - (optional) is a type of number
  num_of_subnet_pairs = null
  # region - (optional) is a type of string
  region = null
  # subnet_size - (optional) is a type of number
  subnet_size = null

  subnets = [{
    cidr      = null
    name      = null
    region    = null
    subnet_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Account name. This account will be used to create an Aviatrix VPC."
  type        = string
}

variable "aviatrix_firenet_vpc" {
  description = "(optional) - Specify the VPC as Aviatrix FireNet VPC or not. Required to be false for GCP provider."
  type        = bool
  default     = null
}

variable "aviatrix_transit_vpc" {
  description = "(optional) - Specify the VPC as Aviatrix Transit VPC or not. Required to be false for GCP provider."
  type        = bool
  default     = null
}

variable "cidr" {
  description = "(optional) - Subnet of the VPC to be created. Required to be empty for GCP provider, and non-empty for other providers."
  type        = string
  default     = null
}

variable "cloud_type" {
  description = "(required) - Type of cloud service provider."
  type        = number
}

variable "enable_native_gwlb" {
  description = "(optional) - Enable Native AWS GWLB for FireNet Function. Only valid with cloud_type = 1 (AWS). Valid values: true or false. Default value: false. Available as of provider version R2.18+."
  type        = bool
  default     = null
}

variable "enable_private_oob_subnet" {
  description = "(optional) - Switch to enable private oob subnet. Only supported for AWS/AWSGOV provider. Valid values: true, false. Default value: false."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the VPC to be created."
  type        = string
}

variable "num_of_subnet_pairs" {
  description = "(optional) - Number of public subnet and private subnet pair to be created."
  type        = number
  default     = null
}

variable "region" {
  description = "(optional) - Region of cloud provider. Required to be empty for GCP provider, and non-empty for other providers."
  type        = string
  default     = null
}

variable "subnet_size" {
  description = "(optional) - Subnet size."
  type        = number
  default     = null
}

variable "subnets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cidr      = string
      name      = string
      region    = string
      subnet_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_vpc" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # aviatrix_firenet_vpc - (optional) is a type of bool
  aviatrix_firenet_vpc = var.aviatrix_firenet_vpc
  # aviatrix_transit_vpc - (optional) is a type of bool
  aviatrix_transit_vpc = var.aviatrix_transit_vpc
  # cidr - (optional) is a type of string
  cidr = var.cidr
  # cloud_type - (required) is a type of number
  cloud_type = var.cloud_type
  # enable_native_gwlb - (optional) is a type of bool
  enable_native_gwlb = var.enable_native_gwlb
  # enable_private_oob_subnet - (optional) is a type of bool
  enable_private_oob_subnet = var.enable_private_oob_subnet
  # name - (required) is a type of string
  name = var.name
  # num_of_subnet_pairs - (optional) is a type of number
  num_of_subnet_pairs = var.num_of_subnet_pairs
  # region - (optional) is a type of string
  region = var.region
  # subnet_size - (optional) is a type of number
  subnet_size = var.subnet_size

  dynamic "subnets" {
    for_each = var.subnets
    content {
      # cidr - (optional) is a type of string
      cidr = subnets.value["cidr"]
      # name - (optional) is a type of string
      name = subnets.value["name"]
      # region - (optional) is a type of string
      region = subnets.value["region"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "azure_vnet_resource_id" {
  description = "returns a string"
  value       = aviatrix_vpc.this.azure_vnet_resource_id
}

output "id" {
  description = "returns a string"
  value       = aviatrix_vpc.this.id
}

output "private_subnets" {
  description = "returns a list of object"
  value       = aviatrix_vpc.this.private_subnets
}

output "public_subnets" {
  description = "returns a list of object"
  value       = aviatrix_vpc.this.public_subnets
}

output "resource_group" {
  description = "returns a string"
  value       = aviatrix_vpc.this.resource_group
}

output "route_tables" {
  description = "returns a list of string"
  value       = aviatrix_vpc.this.route_tables
}

output "vpc_id" {
  description = "returns a string"
  value       = aviatrix_vpc.this.vpc_id
}

output "this" {
  value = aviatrix_vpc.this
}
```

[top](#index)