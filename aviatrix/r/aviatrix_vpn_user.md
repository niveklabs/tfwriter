# aviatrix_vpn_user

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
module "aviatrix_vpn_user" {
  source = "./modules/aviatrix/r/aviatrix_vpn_user"

  # dns_name - (optional) is a type of string
  dns_name = null
  # gw_name - (optional) is a type of string
  gw_name = null
  # manage_user_attachment - (optional) is a type of bool
  manage_user_attachment = null
  # profiles - (optional) is a type of list of string
  profiles = []
  # saml_endpoint - (optional) is a type of string
  saml_endpoint = null
  # user_email - (optional) is a type of string
  user_email = null
  # user_name - (required) is a type of string
  user_name = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_name" {
  description = "(optional) - FQDN of a DNS based VPN service such as GeoVPN or UDP load balancer."
  type        = string
  default     = null
}

variable "gw_name" {
  description = "(optional) - If ELB is enabled, this will be the name of the ELB, else it will be the name of the Aviatrix VPN gateway."
  type        = string
  default     = null
}

variable "manage_user_attachment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "profiles" {
  description = "(optional) - List of profiles for user to attach to."
  type        = list(string)
  default     = null
}

variable "saml_endpoint" {
  description = "(optional) - This is the name of the SAML endpoint to which the user will be associated."
  type        = string
  default     = null
}

variable "user_email" {
  description = "(optional) - VPN User's email."
  type        = string
  default     = null
}

variable "user_name" {
  description = "(required) - VPN user name."
  type        = string
}

variable "vpc_id" {
  description = "(optional) - VPC Id of Aviatrix VPN gateway."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_vpn_user" "this" {
  # dns_name - (optional) is a type of string
  dns_name = var.dns_name
  # gw_name - (optional) is a type of string
  gw_name = var.gw_name
  # manage_user_attachment - (optional) is a type of bool
  manage_user_attachment = var.manage_user_attachment
  # profiles - (optional) is a type of list of string
  profiles = var.profiles
  # saml_endpoint - (optional) is a type of string
  saml_endpoint = var.saml_endpoint
  # user_email - (optional) is a type of string
  user_email = var.user_email
  # user_name - (required) is a type of string
  user_name = var.user_name
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_vpn_user.this.id
}

output "this" {
  value = aviatrix_vpn_user.this
}
```

[top](#index)