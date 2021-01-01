# aws_db_event_categories

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
module "aws_db_event_categories" {
  source = "./modules/aws/d/aws_db_event_categories"

  # source_type - (optional) is a type of string
  source_type = null
}
```

[top](#index)

### Variables

```hcl
variable "source_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_db_event_categories" "this" {
  source_type = var.source_type
}
```

[top](#index)

### Outputs

```hcl
output "event_categories" {
  description = "returns a set of string"
  value       = data.aws_db_event_categories.this.event_categories
}

output "id" {
  description = "returns a string"
  value       = data.aws_db_event_categories.this.id
}

output "this" {
  value = aws_db_event_categories.this
}
```

[top](#index)