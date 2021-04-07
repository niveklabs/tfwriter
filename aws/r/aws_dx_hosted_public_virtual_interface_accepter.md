# aws_dx_hosted_public_virtual_interface_accepter

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
module "aws_dx_hosted_public_virtual_interface_accepter" {
  source = "./modules/aws/r/aws_dx_hosted_public_virtual_interface_accepter"

  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_interface_id - (required) is a type of string
  virtual_interface_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_interface_id" {
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
resource "aws_dx_hosted_public_virtual_interface_accepter" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags
  # virtual_interface_id - (required) is a type of string
  virtual_interface_id = var.virtual_interface_id

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
output "arn" {
  description = "returns a string"
  value       = aws_dx_hosted_public_virtual_interface_accepter.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_dx_hosted_public_virtual_interface_accepter.this.id
}

output "this" {
  value = aws_dx_hosted_public_virtual_interface_accepter.this
}
```

[top](#index)