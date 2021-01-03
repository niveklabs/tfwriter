# aviatrix_device_aws_tgw_attachment

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
module "aviatrix_device_aws_tgw_attachment" {
  source = "./modules/aviatrix/r/aviatrix_device_aws_tgw_attachment"

  # aws_tgw_name - (required) is a type of string
  aws_tgw_name = null
  # connection_name - (required) is a type of string
  connection_name = null
  # device_bgp_asn - (required) is a type of number
  device_bgp_asn = null
  # device_name - (required) is a type of string
  device_name = null
  # security_domain_name - (required) is a type of string
  security_domain_name = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_tgw_name" {
  description = "(required) - AWS TGW name."
  type        = string
}

variable "connection_name" {
  description = "(required) - Connection name."
  type        = string
}

variable "device_bgp_asn" {
  description = "(required) - Device BGP AS Number."
  type        = number
}

variable "device_name" {
  description = "(required) - Device name."
  type        = string
}

variable "security_domain_name" {
  description = "(required) - Security domain name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_device_aws_tgw_attachment" "this" {
  aws_tgw_name         = var.aws_tgw_name
  connection_name      = var.connection_name
  device_bgp_asn       = var.device_bgp_asn
  device_name          = var.device_name
  security_domain_name = var.security_domain_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_device_aws_tgw_attachment.this.id
}

output "this" {
  value = aviatrix_device_aws_tgw_attachment.this
}
```

[top](#index)