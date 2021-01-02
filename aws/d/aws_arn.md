# aws_arn

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_arn" {
  source = "./modules/aws/d/aws_arn"

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
data "aws_arn" "this" {
  arn = var.arn
}
```

[top](#index)

### Outputs

```terraform
output "account" {
  description = "returns a string"
  value       = data.aws_arn.this.account
}

output "id" {
  description = "returns a string"
  value       = data.aws_arn.this.id
}

output "partition" {
  description = "returns a string"
  value       = data.aws_arn.this.partition
}

output "region" {
  description = "returns a string"
  value       = data.aws_arn.this.region
}

output "resource" {
  description = "returns a string"
  value       = data.aws_arn.this.resource
}

output "service" {
  description = "returns a string"
  value       = data.aws_arn.this.service
}

output "this" {
  value = aws_arn.this
}
```

[top](#index)