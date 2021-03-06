# aws_vpn_connection_route

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
module "aws_vpn_connection_route" {
  source = "./modules/aws/r/aws_vpn_connection_route"

  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = null
  # vpn_connection_id - (required) is a type of string
  vpn_connection_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination_cidr_block" {
  description = "(required)"
  type        = string
}

variable "vpn_connection_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpn_connection_route" "this" {
  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = var.destination_cidr_block
  # vpn_connection_id - (required) is a type of string
  vpn_connection_id = var.vpn_connection_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_vpn_connection_route.this.id
}

output "this" {
  value = aws_vpn_connection_route.this
}
```

[top](#index)