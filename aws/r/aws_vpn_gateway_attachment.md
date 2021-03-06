# aws_vpn_gateway_attachment

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
module "aws_vpn_gateway_attachment" {
  source = "./modules/aws/r/aws_vpn_gateway_attachment"

  # vpc_id - (required) is a type of string
  vpc_id = null
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "vpn_gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpn_gateway_attachment" "this" {
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = var.vpn_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_vpn_gateway_attachment.this.id
}

output "this" {
  value = aws_vpn_gateway_attachment.this
}
```

[top](#index)