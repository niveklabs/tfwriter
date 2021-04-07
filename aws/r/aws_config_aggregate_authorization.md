# aws_config_aggregate_authorization

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
module "aws_config_aggregate_authorization" {
  source = "./modules/aws/r/aws_config_aggregate_authorization"

  # account_id - (required) is a type of string
  account_id = null
  # region - (required) is a type of string
  region = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_aggregate_authorization" "this" {
  # account_id - (required) is a type of string
  account_id = var.account_id
  # region - (required) is a type of string
  region = var.region
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_config_aggregate_authorization.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_config_aggregate_authorization.this.id
}

output "this" {
  value = aws_config_aggregate_authorization.this
}
```

[top](#index)