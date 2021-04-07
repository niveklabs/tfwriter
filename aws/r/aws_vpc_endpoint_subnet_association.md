# aws_vpc_endpoint_subnet_association

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

```terraform
variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "vpc_endpoint_id" {
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
resource "aws_vpc_endpoint_subnet_association" "this" {
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # vpc_endpoint_id - (required) is a type of string
  vpc_endpoint_id = var.vpc_endpoint_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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
  value       = aws_vpc_endpoint_subnet_association.this.id
}

output "this" {
  value = aws_vpc_endpoint_subnet_association.this
}
```

[top](#index)