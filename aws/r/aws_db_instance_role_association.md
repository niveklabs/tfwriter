# aws_db_instance_role_association

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
module "aws_db_instance_role_association" {
  source = "./modules/aws/r/aws_db_instance_role_association"

  # db_instance_identifier - (required) is a type of string
  db_instance_identifier = null
  # feature_name - (required) is a type of string
  feature_name = null
  # role_arn - (required) is a type of string
  role_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "db_instance_identifier" {
  description = "(required)"
  type        = string
}

variable "feature_name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_db_instance_role_association" "this" {
  db_instance_identifier = var.db_instance_identifier
  feature_name           = var.feature_name
  role_arn               = var.role_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_db_instance_role_association.this.id
}

output "this" {
  value = aws_db_instance_role_association.this
}
```

[top](#index)