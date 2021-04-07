# aws_cloudwatch_query_definition

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_cloudwatch_query_definition" {
  source = "./modules/aws/r/aws_cloudwatch_query_definition"

  # log_group_names - (optional) is a type of list of string
  log_group_names = []
  # name - (required) is a type of string
  name = null
  # query_string - (required) is a type of string
  query_string = null
}
```

[top](#index)

### Variables

```terraform
variable "log_group_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query_string" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_query_definition" "this" {
  # log_group_names - (optional) is a type of list of string
  log_group_names = var.log_group_names
  # name - (required) is a type of string
  name = var.name
  # query_string - (required) is a type of string
  query_string = var.query_string
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_query_definition.this.id
}

output "query_definition_id" {
  description = "returns a string"
  value       = aws_cloudwatch_query_definition.this.query_definition_id
}

output "this" {
  value = aws_cloudwatch_query_definition.this
}
```

[top](#index)