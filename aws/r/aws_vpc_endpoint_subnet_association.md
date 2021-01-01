# aws_vpc_endpoint_subnet_association

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_vpc_endpoint_subnet_association" {
  source = "./modules/aws/r/aws_vpc_endpoint_subnet_association"

  # subnet_id - (required) is a type of string
  subnet_id = null
  # vpc_endpoint_id - (required) is a type of string
  vpc_endpoint_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "vpc_endpoint_id" {
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
resource "aws_vpc_endpoint_subnet_association" "this" {
  subnet_id       = var.subnet_id
  vpc_endpoint_id = var.vpc_endpoint_id

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
  value       = aws_vpc_endpoint_subnet_association.this.id
}

output "this" {
  value = aws_vpc_endpoint_subnet_association.this
}
```

[top](#index)