# aws_lakeformation_resource

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lakeformation_resource" {
  source = "./modules/aws/d/aws_lakeformation_resource"

  # arn - (required) is a type of string
  arn = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_lakeformation_resource" "this" {
  arn = var.arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_lakeformation_resource.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = data.aws_lakeformation_resource.this.last_modified
}

output "role_arn" {
  description = "returns a string"
  value       = data.aws_lakeformation_resource.this.role_arn
}

output "this" {
  value = aws_lakeformation_resource.this
}
```

[top](#index)