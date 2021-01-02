# aws_db_subnet_group

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
module "aws_db_subnet_group" {
  source = "./modules/aws/d/aws_db_subnet_group"

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
data "aws_db_subnet_group" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_db_subnet_group.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_db_subnet_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_db_subnet_group.this.id
}

output "status" {
  description = "returns a string"
  value       = data.aws_db_subnet_group.this.status
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = data.aws_db_subnet_group.this.subnet_ids
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_db_subnet_group.this.vpc_id
}

output "this" {
  value = aws_db_subnet_group.this
}
```

[top](#index)