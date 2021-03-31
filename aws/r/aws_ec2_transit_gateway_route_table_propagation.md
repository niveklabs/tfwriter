# aws_ec2_transit_gateway_route_table_propagation

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
module "aws_ec2_transit_gateway_route_table_propagation" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_route_table_propagation"

  # transit_gateway_attachment_id - (required) is a type of string
  transit_gateway_attachment_id = null
  # transit_gateway_route_table_id - (required) is a type of string
  transit_gateway_route_table_id = null
}
```

[top](#index)

### Variables

```terraform
variable "transit_gateway_attachment_id" {
  description = "(required)"
  type        = string
}

variable "transit_gateway_route_table_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_transit_gateway_route_table_propagation" "this" {
  transit_gateway_attachment_id  = var.transit_gateway_attachment_id
  transit_gateway_route_table_id = var.transit_gateway_route_table_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_route_table_propagation.this.id
}

output "resource_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_route_table_propagation.this.resource_id
}

output "resource_type" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_route_table_propagation.this.resource_type
}

output "this" {
  value = aws_ec2_transit_gateway_route_table_propagation.this
}
```

[top](#index)