# aws_sfn_activity

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
module "aws_sfn_activity" {
  source = "./modules/aws/d/aws_sfn_activity"

  # arn - (optional) is a type of string
  arn = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_sfn_activity" "this" {
  # arn - (optional) is a type of string
  arn = var.arn
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_sfn_activity.this.arn
}

output "creation_date" {
  description = "returns a string"
  value       = data.aws_sfn_activity.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = data.aws_sfn_activity.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_sfn_activity.this.name
}

output "this" {
  value = aws_sfn_activity.this
}
```

[top](#index)