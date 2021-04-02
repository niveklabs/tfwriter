# aws_ram_resource_association

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
module "aws_ram_resource_association" {
  source = "./modules/aws/r/aws_ram_resource_association"

  # resource_arn - (required) is a type of string
  resource_arn = null
  # resource_share_arn - (required) is a type of string
  resource_share_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_arn" {
  description = "(required)"
  type        = string
}

variable "resource_share_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ram_resource_association" "this" {
  resource_arn       = var.resource_arn
  resource_share_arn = var.resource_share_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ram_resource_association.this.id
}

output "this" {
  value = aws_ram_resource_association.this
}
```

[top](#index)