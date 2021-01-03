# aviatrix_geo_vpn

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
module "aviatrix_geo_vpn" {
  source = "./modules/aviatrix/r/aviatrix_geo_vpn"

  # account_name - (required) is a type of string
  account_name = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # domain_name - (required) is a type of string
  domain_name = null
  # elb_dns_names - (required) is a type of list of string
  elb_dns_names = []
  # service_name - (required) is a type of string
  service_name = null
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
  description = "(required) - Type of cloud service provider, requires an integer value. Currently only AWS(1) is supported."
  type        = number
}

variable "domain_name" {
  description = "(required) - The hosted domain name. It must be hosted by AWS Route53 or Azure DNS in the selected account."
  type        = string
}

variable "elb_dns_names" {
  description = "(required) - List of ELB names to attach to this Geo VPN name."
  type        = list(string)
}

variable "service_name" {
  description = "(required) - The hostname that users will connect to. A DNS record will be created for this name in the specified domain name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_geo_vpn" "this" {
  account_name  = var.account_name
  cloud_type    = var.cloud_type
  domain_name   = var.domain_name
  elb_dns_names = var.elb_dns_names
  service_name  = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_geo_vpn.this.id
}

output "this" {
  value = aviatrix_geo_vpn.this
}
```

[top](#index)