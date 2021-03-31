# aws_opsworks_rds_db_instance

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_opsworks_rds_db_instance" {
  source = "./modules/aws/r/aws_opsworks_rds_db_instance"

  # db_password - (required) is a type of string
  db_password = null
  # db_user - (required) is a type of string
  db_user = null
  # rds_db_instance_arn - (required) is a type of string
  rds_db_instance_arn = null
  # stack_id - (required) is a type of string
  stack_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_password" {
  description = "(required)"
  type        = string
}

variable "db_user" {
  description = "(required)"
  type        = string
}

variable "rds_db_instance_arn" {
  description = "(required)"
  type        = string
}

variable "stack_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_opsworks_rds_db_instance" "this" {
  db_password         = var.db_password
  db_user             = var.db_user
  rds_db_instance_arn = var.rds_db_instance_arn
  stack_id            = var.stack_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_opsworks_rds_db_instance.this.id
}

output "this" {
  value = aws_opsworks_rds_db_instance.this
}
```

[top](#index)