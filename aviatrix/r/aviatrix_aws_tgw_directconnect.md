# aviatrix_aws_tgw_directconnect

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
module "aviatrix_aws_tgw_directconnect" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_directconnect"

  # allowed_prefix - (required) is a type of string
  allowed_prefix = null
  # directconnect_account_name - (required) is a type of string
  directconnect_account_name = null
  # dx_gateway_id - (required) is a type of string
  dx_gateway_id = null
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = null
  # security_domain_name - (required) is a type of string
  security_domain_name = null
  # tgw_name - (required) is a type of string
  tgw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_prefix" {
  description = "(required) - Public IP address. Example: '40.0.0.0'."
  type        = string
}

variable "directconnect_account_name" {
  description = "(required) - This parameter represents the name of an Account in Aviatrix controller."
  type        = string
}

variable "dx_gateway_id" {
  description = "(required) - This parameter represents the name of a Direct Connect Gateway ID."
  type        = string
}

variable "enable_learned_cidrs_approval" {
  description = "(optional) - Switch to enable/disable encrypted transit approval for direct connection. Valid values: true, false."
  type        = bool
  default     = null
}

variable "security_domain_name" {
  description = "(required) - The name of an Aviatrix security domain, to which the direct connect gateway will be attached."
  type        = string
}

variable "tgw_name" {
  description = "(required) - This parameter represents the name of an AWS TGW."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_directconnect" "this" {
  # allowed_prefix - (required) is a type of string
  allowed_prefix = var.allowed_prefix
  # directconnect_account_name - (required) is a type of string
  directconnect_account_name = var.directconnect_account_name
  # dx_gateway_id - (required) is a type of string
  dx_gateway_id = var.dx_gateway_id
  # enable_learned_cidrs_approval - (optional) is a type of bool
  enable_learned_cidrs_approval = var.enable_learned_cidrs_approval
  # security_domain_name - (required) is a type of string
  security_domain_name = var.security_domain_name
  # tgw_name - (required) is a type of string
  tgw_name = var.tgw_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_directconnect.this.id
}

output "this" {
  value = aviatrix_aws_tgw_directconnect.this
}
```

[top](#index)