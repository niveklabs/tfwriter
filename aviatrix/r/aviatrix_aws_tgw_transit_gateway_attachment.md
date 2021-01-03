# aviatrix_aws_tgw_transit_gateway_attachment

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
module "aviatrix_aws_tgw_transit_gateway_attachment" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_transit_gateway_attachment"

  # region - (required) is a type of string
  region = null
  # tgw_name - (required) is a type of string
  tgw_name = null
  # transit_gateway_name - (required) is a type of string
  transit_gateway_name = null
  # vpc_account_name - (required) is a type of string
  vpc_account_name = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "region" {
  description = "(required) - Region of cloud provider."
  type        = string
}

variable "tgw_name" {
  description = "(required) - Name of the AWS TGW."
  type        = string
}

variable "transit_gateway_name" {
  description = "(required) - Name of the transit gateway to be attached to tgw."
  type        = string
}

variable "vpc_account_name" {
  description = "(required) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
}

variable "vpc_id" {
  description = "(required) - This parameter represents the ID of the VPC."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_transit_gateway_attachment" "this" {
  region               = var.region
  tgw_name             = var.tgw_name
  transit_gateway_name = var.transit_gateway_name
  vpc_account_name     = var.vpc_account_name
  vpc_id               = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_transit_gateway_attachment.this.id
}

output "this" {
  value = aviatrix_aws_tgw_transit_gateway_attachment.this
}
```

[top](#index)