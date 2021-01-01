# aws_cloudwatch_log_subscription_filter

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
module "aws_cloudwatch_log_subscription_filter" {
  source = "./modules/aws/r/aws_cloudwatch_log_subscription_filter"

  # destination_arn - (required) is a type of string
  destination_arn = null
  # distribution - (optional) is a type of string
  distribution = null
  # filter_pattern - (required) is a type of string
  filter_pattern = null
  # log_group_name - (required) is a type of string
  log_group_name = null
  # name - (required) is a type of string
  name = null
  # role_arn - (optional) is a type of string
  role_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "destination_arn" {
  description = "(required)"
  type        = string
}

variable "distribution" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_pattern" {
  description = "(required)"
  type        = string
}

variable "log_group_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_cloudwatch_log_subscription_filter" "this" {
  destination_arn = var.destination_arn
  distribution    = var.distribution
  filter_pattern  = var.filter_pattern
  log_group_name  = var.log_group_name
  name            = var.name
  role_arn        = var.role_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_subscription_filter.this.id
}

output "role_arn" {
  description = "returns a string"
  value       = aws_cloudwatch_log_subscription_filter.this.role_arn
}

output "this" {
  value = aws_cloudwatch_log_subscription_filter.this
}
```

[top](#index)