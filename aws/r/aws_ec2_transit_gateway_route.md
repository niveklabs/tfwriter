# aws_ec2_transit_gateway_route

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ec2_transit_gateway_route" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_route"

  # blackhole - (optional) is a type of bool
  blackhole = null
  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = null
  # transit_gateway_attachment_id - (optional) is a type of string
  transit_gateway_attachment_id = null
  # transit_gateway_route_table_id - (required) is a type of string
  transit_gateway_route_table_id = null
}
```

[top](#index)

### Variables

```terraform
variable "blackhole" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "destination_cidr_block" {
  description = "(required)"
  type        = string
}

variable "transit_gateway_attachment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transit_gateway_route_table_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_transit_gateway_route" "this" {
  blackhole                      = var.blackhole
  destination_cidr_block         = var.destination_cidr_block
  transit_gateway_attachment_id  = var.transit_gateway_attachment_id
  transit_gateway_route_table_id = var.transit_gateway_route_table_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_route.this.id
}

output "this" {
  value = aws_ec2_transit_gateway_route.this
}
```

[top](#index)