# aws_ec2_transit_gateway_peering_attachment

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
module "aws_ec2_transit_gateway_peering_attachment" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_peering_attachment"

  # peer_account_id - (optional) is a type of string
  peer_account_id = null
  # peer_region - (required) is a type of string
  peer_region = null
  # peer_transit_gateway_id - (required) is a type of string
  peer_transit_gateway_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_id - (required) is a type of string
  transit_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "peer_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_region" {
  description = "(required)"
  type        = string
}

variable "peer_transit_gateway_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transit_gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_transit_gateway_peering_attachment" "this" {
  peer_account_id         = var.peer_account_id
  peer_region             = var.peer_region
  peer_transit_gateway_id = var.peer_transit_gateway_id
  tags                    = var.tags
  transit_gateway_id      = var.transit_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment.this.id
}

output "peer_account_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment.this.peer_account_id
}

output "this" {
  value = aws_ec2_transit_gateway_peering_attachment.this
}
```

[top](#index)