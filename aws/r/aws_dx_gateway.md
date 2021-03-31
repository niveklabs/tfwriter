# aws_dx_gateway

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
module "aws_dx_gateway" {
  source = "./modules/aws/r/aws_dx_gateway"

  # amazon_side_asn - (required) is a type of string
  amazon_side_asn = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "amazon_side_asn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dx_gateway" "this" {
  amazon_side_asn = var.amazon_side_asn
  name            = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_dx_gateway.this.id
}

output "owner_account_id" {
  description = "returns a string"
  value       = aws_dx_gateway.this.owner_account_id
}

output "this" {
  value = aws_dx_gateway.this
}
```

[top](#index)