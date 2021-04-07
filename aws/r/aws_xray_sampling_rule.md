# aws_xray_sampling_rule

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
module "aws_xray_sampling_rule" {
  source = "./modules/aws/r/aws_xray_sampling_rule"

  # attributes - (optional) is a type of map of string
  attributes = {}
  # fixed_rate - (required) is a type of number
  fixed_rate = null
  # host - (required) is a type of string
  host = null
  # http_method - (required) is a type of string
  http_method = null
  # priority - (required) is a type of number
  priority = null
  # reservoir_size - (required) is a type of number
  reservoir_size = null
  # resource_arn - (required) is a type of string
  resource_arn = null
  # rule_name - (optional) is a type of string
  rule_name = null
  # service_name - (required) is a type of string
  service_name = null
  # service_type - (required) is a type of string
  service_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # url_path - (required) is a type of string
  url_path = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "attributes" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "fixed_rate" {
  description = "(required)"
  type        = number
}

variable "host" {
  description = "(required)"
  type        = string
}

variable "http_method" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "reservoir_size" {
  description = "(required)"
  type        = number
}

variable "resource_arn" {
  description = "(required)"
  type        = string
}

variable "rule_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "service_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "url_path" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "aws_xray_sampling_rule" "this" {
  # attributes - (optional) is a type of map of string
  attributes = var.attributes
  # fixed_rate - (required) is a type of number
  fixed_rate = var.fixed_rate
  # host - (required) is a type of string
  host = var.host
  # http_method - (required) is a type of string
  http_method = var.http_method
  # priority - (required) is a type of number
  priority = var.priority
  # reservoir_size - (required) is a type of number
  reservoir_size = var.reservoir_size
  # resource_arn - (required) is a type of string
  resource_arn = var.resource_arn
  # rule_name - (optional) is a type of string
  rule_name = var.rule_name
  # service_name - (required) is a type of string
  service_name = var.service_name
  # service_type - (required) is a type of string
  service_type = var.service_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # url_path - (required) is a type of string
  url_path = var.url_path
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_xray_sampling_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_xray_sampling_rule.this.id
}

output "this" {
  value = aws_xray_sampling_rule.this
}
```

[top](#index)