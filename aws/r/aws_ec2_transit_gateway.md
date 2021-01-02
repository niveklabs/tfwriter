# aws_ec2_transit_gateway

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_transit_gateway" {
  source = "./modules/aws/r/aws_ec2_transit_gateway"

  # amazon_side_asn - (optional) is a type of number
  amazon_side_asn = null
  # auto_accept_shared_attachments - (optional) is a type of string
  auto_accept_shared_attachments = null
  # default_route_table_association - (optional) is a type of string
  default_route_table_association = null
  # default_route_table_propagation - (optional) is a type of string
  default_route_table_propagation = null
  # description - (optional) is a type of string
  description = null
  # dns_support - (optional) is a type of string
  dns_support = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpn_ecmp_support - (optional) is a type of string
  vpn_ecmp_support = null
}
```

[top](#index)

### Variables

```terraform
variable "amazon_side_asn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_accept_shared_attachments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_route_table_association" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_route_table_propagation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpn_ecmp_support" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_transit_gateway" "this" {
  amazon_side_asn                 = var.amazon_side_asn
  auto_accept_shared_attachments  = var.auto_accept_shared_attachments
  default_route_table_association = var.default_route_table_association
  default_route_table_propagation = var.default_route_table_propagation
  description                     = var.description
  dns_support                     = var.dns_support
  tags                            = var.tags
  vpn_ecmp_support                = var.vpn_ecmp_support
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway.this.arn
}

output "association_default_route_table_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway.this.association_default_route_table_id
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway.this.owner_id
}

output "propagation_default_route_table_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway.this.propagation_default_route_table_id
}

output "this" {
  value = aws_ec2_transit_gateway.this
}
```

[top](#index)