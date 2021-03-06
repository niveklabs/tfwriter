# aws_elastic_beanstalk_solution_stack

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
module "aws_elastic_beanstalk_solution_stack" {
  source = "./modules/aws/d/aws_elastic_beanstalk_solution_stack"

  # most_recent - (optional) is a type of bool
  most_recent = null
  # name_regex - (required) is a type of string
  name_regex = null
}
```

[top](#index)

### Variables

```terraform
variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name_regex" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_elastic_beanstalk_solution_stack" "this" {
  # most_recent - (optional) is a type of bool
  most_recent = var.most_recent
  # name_regex - (required) is a type of string
  name_regex = var.name_regex
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_elastic_beanstalk_solution_stack.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_elastic_beanstalk_solution_stack.this.name
}

output "this" {
  value = aws_elastic_beanstalk_solution_stack.this
}
```

[top](#index)