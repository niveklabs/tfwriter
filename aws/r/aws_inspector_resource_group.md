# aws_inspector_resource_group

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_inspector_resource_group" {
  source = "./modules/aws/r/aws_inspector_resource_group"

  # tags - (required) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(required)"
  type        = map(string)
}
```

[top](#index)

### Resource

```terraform
resource "aws_inspector_resource_group" "this" {
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_inspector_resource_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_inspector_resource_group.this.id
}

output "this" {
  value = aws_inspector_resource_group.this
}
```

[top](#index)