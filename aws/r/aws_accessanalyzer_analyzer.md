# aws_accessanalyzer_analyzer

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
module "aws_accessanalyzer_analyzer" {
  source = "./modules/aws/r/aws_accessanalyzer_analyzer"

  # analyzer_name - (required) is a type of string
  analyzer_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "analyzer_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_accessanalyzer_analyzer" "this" {
  # analyzer_name - (required) is a type of string
  analyzer_name = var.analyzer_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_accessanalyzer_analyzer.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_accessanalyzer_analyzer.this.id
}

output "this" {
  value = aws_accessanalyzer_analyzer.this
}
```

[top](#index)