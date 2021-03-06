# aws_ec2_transit_gateway_peering_attachment_accepter

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_transit_gateway_peering_attachment_accepter" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_peering_attachment_accepter"

  # tags - (optional) is a type of map of string
  tags = {}
  # transit_gateway_attachment_id - (required) is a type of string
  transit_gateway_attachment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transit_gateway_attachment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_transit_gateway_peering_attachment_accepter" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags
  # transit_gateway_attachment_id - (required) is a type of string
  transit_gateway_attachment_id = var.transit_gateway_attachment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment_accepter.this.id
}

output "peer_account_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment_accepter.this.peer_account_id
}

output "peer_region" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment_accepter.this.peer_region
}

output "peer_transit_gateway_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment_accepter.this.peer_transit_gateway_id
}

output "transit_gateway_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_peering_attachment_accepter.this.transit_gateway_id
}

output "this" {
  value = aws_ec2_transit_gateway_peering_attachment_accepter.this
}
```

[top](#index)