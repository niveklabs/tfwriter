# aws_vpc_ipv4_cidr_block_association

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_vpc_ipv4_cidr_block_association" {
  source = "./modules/aws/r/aws_vpc_ipv4_cidr_block_association"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "aws_vpc_ipv4_cidr_block_association" "this" {
  cidr_block = var.cidr_block
  vpc_id     = var.vpc_id

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

```hcl
output "id" {
  description = "returns a string"
  value       = aws_vpc_ipv4_cidr_block_association.this.id
}

output "this" {
  value = aws_vpc_ipv4_cidr_block_association.this
}
```

[top](#index)