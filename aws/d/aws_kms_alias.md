# aws_kms_alias

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
module "aws_kms_alias" {
  source = "./modules/aws/d/aws_kms_alias"

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
data "aws_kms_alias" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_kms_alias.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_kms_alias.this.id
}

output "target_key_arn" {
  description = "returns a string"
  value       = data.aws_kms_alias.this.target_key_arn
}

output "target_key_id" {
  description = "returns a string"
  value       = data.aws_kms_alias.this.target_key_id
}

output "this" {
  value = aws_kms_alias.this
}
```

[top](#index)