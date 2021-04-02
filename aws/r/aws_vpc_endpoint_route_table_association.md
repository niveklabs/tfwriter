# aws_vpc_endpoint_route_table_association

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
module "aws_vpc_endpoint_route_table_association" {
  source = "./modules/aws/r/aws_vpc_endpoint_route_table_association"

  # route_table_id - (required) is a type of string
  route_table_id = null
  # vpc_endpoint_id - (required) is a type of string
  vpc_endpoint_id = null
}
```

[top](#index)

### Variables

```terraform
variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "vpc_endpoint_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc_endpoint_route_table_association" "this" {
  route_table_id  = var.route_table_id
  vpc_endpoint_id = var.vpc_endpoint_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_vpc_endpoint_route_table_association.this.id
}

output "this" {
  value = aws_vpc_endpoint_route_table_association.this
}
```

[top](#index)