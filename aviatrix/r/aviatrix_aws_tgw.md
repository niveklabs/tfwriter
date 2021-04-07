# aviatrix_aws_tgw

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
module "aviatrix_aws_tgw" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw"

  # account_name - (required) is a type of string
  account_name = null
  # attached_aviatrix_transit_gateway - (optional) is a type of list of string
  attached_aviatrix_transit_gateway = []
  # aws_side_as_number - (required) is a type of string
  aws_side_as_number = null
  # cidrs - (optional) is a type of set of string
  cidrs = []
  # cloud_type - (optional) is a type of number
  cloud_type = null
  # enable_multicast - (optional) is a type of bool
  enable_multicast = null
  # manage_transit_gateway_attachment - (optional) is a type of bool
  manage_transit_gateway_attachment = null
  # manage_vpc_attachment - (optional) is a type of bool
  manage_vpc_attachment = null
  # region - (required) is a type of string
  region = null
  # tgw_name - (required) is a type of string
  tgw_name = null

  security_domains = [{
    attached_vpc = [{
      customized_route_advertisement  = null
      customized_routes               = null
      disable_local_route_propagation = null
      route_tables                    = null
      subnets                         = null
      vpc_account_name                = null
      vpc_id                          = null
      vpc_region                      = null
    }]
    aviatrix_firewall    = null
    connected_domains    = []
    native_egress        = null
    native_firewall      = null
    security_domain_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
}

variable "attached_aviatrix_transit_gateway" {
  description = "(optional) - A list of Names of Aviatrix Transit Gateway to attach to one of the three default domains."
  type        = list(string)
  default     = null
}

variable "aws_side_as_number" {
  description = "(required) - BGP Local ASN (Autonomous System Number), Integer between 1-4294967294."
  type        = string
}

variable "cidrs" {
  description = "(optional) - TGW CIDRs."
  type        = set(string)
  default     = null
}

variable "cloud_type" {
  description = "(optional) - Type of cloud service provider, requires an integer value. Supported for AWS (1) and AWS GOV (256). Default value: 1."
  type        = number
  default     = null
}

variable "enable_multicast" {
  description = "(optional) - Enable Multicast."
  type        = bool
  default     = null
}

variable "manage_transit_gateway_attachment" {
  description = "(optional) - This parameter is a switch used to determine whether or not to manage transit gateway attachments to the TGW using the aviatrix_aws_tgw resource. If this is set to false, attachment of transit gateways must be done using the aviatrix_aws_tgw_transit_gateway_attachment resource. Valid values: true, false. Default value: true."
  type        = bool
  default     = null
}

variable "manage_vpc_attachment" {
  description = "(optional) - This parameter is a switch used to determine whether or not to manage VPC attachments to the TGW using the aviatrix_aws_tgw resource. If this is set to false, attachment of VPCs must be done using the aviatrix_aws_tgw_vpc_attachment resource. Valid values: true, false. Default value: true."
  type        = bool
  default     = null
}

variable "region" {
  description = "(required) - Region of cloud provider."
  type        = string
}

variable "tgw_name" {
  description = "(required) - Name of the AWS TGW which is going to be created."
  type        = string
}

variable "security_domains" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      attached_vpc = list(object(
        {
          customized_route_advertisement  = string
          customized_routes               = string
          disable_local_route_propagation = bool
          route_tables                    = string
          subnets                         = string
          vpc_account_name                = string
          vpc_id                          = string
          vpc_region                      = string
        }
      ))
      aviatrix_firewall    = bool
      connected_domains    = list(string)
      native_egress        = bool
      native_firewall      = bool
      security_domain_name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # attached_aviatrix_transit_gateway - (optional) is a type of list of string
  attached_aviatrix_transit_gateway = var.attached_aviatrix_transit_gateway
  # aws_side_as_number - (required) is a type of string
  aws_side_as_number = var.aws_side_as_number
  # cidrs - (optional) is a type of set of string
  cidrs = var.cidrs
  # cloud_type - (optional) is a type of number
  cloud_type = var.cloud_type
  # enable_multicast - (optional) is a type of bool
  enable_multicast = var.enable_multicast
  # manage_transit_gateway_attachment - (optional) is a type of bool
  manage_transit_gateway_attachment = var.manage_transit_gateway_attachment
  # manage_vpc_attachment - (optional) is a type of bool
  manage_vpc_attachment = var.manage_vpc_attachment
  # region - (required) is a type of string
  region = var.region
  # tgw_name - (required) is a type of string
  tgw_name = var.tgw_name

  dynamic "security_domains" {
    for_each = var.security_domains
    content {
      # aviatrix_firewall - (optional) is a type of bool
      aviatrix_firewall = security_domains.value["aviatrix_firewall"]
      # connected_domains - (optional) is a type of list of string
      connected_domains = security_domains.value["connected_domains"]
      # native_egress - (optional) is a type of bool
      native_egress = security_domains.value["native_egress"]
      # native_firewall - (optional) is a type of bool
      native_firewall = security_domains.value["native_firewall"]
      # security_domain_name - (required) is a type of string
      security_domain_name = security_domains.value["security_domain_name"]

      dynamic "attached_vpc" {
        for_each = security_domains.value.attached_vpc
        content {
          # customized_route_advertisement - (optional) is a type of string
          customized_route_advertisement = attached_vpc.value["customized_route_advertisement"]
          # customized_routes - (optional) is a type of string
          customized_routes = attached_vpc.value["customized_routes"]
          # disable_local_route_propagation - (optional) is a type of bool
          disable_local_route_propagation = attached_vpc.value["disable_local_route_propagation"]
          # route_tables - (optional) is a type of string
          route_tables = attached_vpc.value["route_tables"]
          # subnets - (optional) is a type of string
          subnets = attached_vpc.value["subnets"]
          # vpc_account_name - (required) is a type of string
          vpc_account_name = attached_vpc.value["vpc_account_name"]
          # vpc_id - (required) is a type of string
          vpc_id = attached_vpc.value["vpc_id"]
          # vpc_region - (required) is a type of string
          vpc_region = attached_vpc.value["vpc_region"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw.this.id
}

output "this" {
  value = aviatrix_aws_tgw.this
}
```

[top](#index)