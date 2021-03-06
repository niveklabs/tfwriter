# aws_ec2_local_gateway_route

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
module "aws_ec2_local_gateway_route" {
  source = "./modules/aws/r/aws_ec2_local_gateway_route"

  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = null
  # local_gateway_route_table_id - (required) is a type of string
  local_gateway_route_table_id = null
  # local_gateway_virtual_interface_group_id - (required) is a type of string
  local_gateway_virtual_interface_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination_cidr_block" {
  description = "(required)"
  type        = string
}

variable "local_gateway_route_table_id" {
  description = "(required)"
  type        = string
}

variable "local_gateway_virtual_interface_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_local_gateway_route" "this" {
  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = var.destination_cidr_block
  # local_gateway_route_table_id - (required) is a type of string
  local_gateway_route_table_id = var.local_gateway_route_table_id
  # local_gateway_virtual_interface_group_id - (required) is a type of string
  local_gateway_virtual_interface_group_id = var.local_gateway_virtual_interface_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_local_gateway_route.this.id
}

output "this" {
  value = aws_ec2_local_gateway_route.this
}
```

[top](#index)