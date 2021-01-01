# aws_ec2_client_vpn_authorization_rule
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_ec2_client_vpn_authorization_rule" {
  source = "./modules/aws/r/aws_ec2_client_vpn_authorization_rule"

  # access_group_id - (optional) is a type of string
  access_group_id = null
  # authorize_all_groups - (optional) is a type of bool
  authorize_all_groups = null
  # client_vpn_endpoint_id - (required) is a type of string
  client_vpn_endpoint_id = null
  # description - (optional) is a type of string
  description = null
  # target_network_cidr - (required) is a type of string
  target_network_cidr = null
}
```
[top](#index)
### Variables
```hcl
variable "access_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorize_all_groups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "client_vpn_endpoint_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_network_cidr" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_ec2_client_vpn_authorization_rule" "this" {
  access_group_id        = var.access_group_id
  authorize_all_groups   = var.authorize_all_groups
  client_vpn_endpoint_id = var.client_vpn_endpoint_id
  description            = var.description
  target_network_cidr    = var.target_network_cidr
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_authorization_rule.this.id
}

output "this" {
  value = aws_ec2_client_vpn_authorization_rule.this
}
```
[top](#index)
