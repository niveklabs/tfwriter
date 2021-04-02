# aws_mq_configuration

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
module "aws_mq_configuration" {
  source = "./modules/aws/r/aws_mq_configuration"

  # authentication_strategy - (optional) is a type of string
  authentication_strategy = null
  # data - (required) is a type of string
  data = null
  # description - (optional) is a type of string
  description = null
  # engine_type - (required) is a type of string
  engine_type = null
  # engine_version - (required) is a type of string
  engine_version = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "authentication_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_type" {
  description = "(required)"
  type        = string
}

variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "aws_mq_configuration" "this" {
  authentication_strategy = var.authentication_strategy
  data                    = var.data
  description             = var.description
  engine_type             = var.engine_type
  engine_version          = var.engine_version
  name                    = var.name
  tags                    = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_mq_configuration.this.arn
}

output "authentication_strategy" {
  description = "returns a string"
  value       = aws_mq_configuration.this.authentication_strategy
}

output "id" {
  description = "returns a string"
  value       = aws_mq_configuration.this.id
}

output "latest_revision" {
  description = "returns a number"
  value       = aws_mq_configuration.this.latest_revision
}

output "this" {
  value = aws_mq_configuration.this
}
```

[top](#index)