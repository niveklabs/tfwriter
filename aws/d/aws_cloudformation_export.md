# aws_cloudformation_export

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_cloudformation_export" {
  source = "./modules/aws/d/aws_cloudformation_export"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_cloudformation_export" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "exporting_stack_id" {
  description = "returns a string"
  value       = data.aws_cloudformation_export.this.exporting_stack_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudformation_export.this.id
}

output "value" {
  description = "returns a string"
  value       = data.aws_cloudformation_export.this.value
}

output "this" {
  value = aws_cloudformation_export.this
}
```

[top](#index)