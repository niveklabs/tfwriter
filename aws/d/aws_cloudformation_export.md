# aws_cloudformation_export

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
module "aws_cloudformation_export" {
  source = "./modules/aws/d/aws_cloudformation_export"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_cloudformation_export" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
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