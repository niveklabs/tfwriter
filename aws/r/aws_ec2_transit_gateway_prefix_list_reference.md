# aws_ec2_transit_gateway_prefix_list_reference

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
module "aws_ec2_transit_gateway_prefix_list_reference" {
  source = "./modules/aws/r/aws_ec2_transit_gateway_prefix_list_reference"

  # blackhole - (optional) is a type of bool
  blackhole = null
  # prefix_list_id - (required) is a type of string
  prefix_list_id = null
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

variable "prefix_list_id" {
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
resource "aws_ec2_transit_gateway_prefix_list_reference" "this" {
  blackhole                      = var.blackhole
  prefix_list_id                 = var.prefix_list_id
  transit_gateway_attachment_id  = var.transit_gateway_attachment_id
  transit_gateway_route_table_id = var.transit_gateway_route_table_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_prefix_list_reference.this.id
}

output "prefix_list_owner_id" {
  description = "returns a string"
  value       = aws_ec2_transit_gateway_prefix_list_reference.this.prefix_list_owner_id
}

output "this" {
  value = aws_ec2_transit_gateway_prefix_list_reference.this
}
```

[top](#index)