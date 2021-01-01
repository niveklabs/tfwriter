# aws_waf_regex_pattern_set

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_waf_regex_pattern_set" {
  source = "./modules/aws/r/aws_waf_regex_pattern_set"

  # name - (required) is a type of string
  name = null
  # regex_pattern_strings - (optional) is a type of set of string
  regex_pattern_strings = []
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "regex_pattern_strings" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_waf_regex_pattern_set" "this" {
  name                  = var.name
  regex_pattern_strings = var.regex_pattern_strings
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_waf_regex_pattern_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_waf_regex_pattern_set.this.id
}

output "this" {
  value = aws_waf_regex_pattern_set.this
}
```

[top](#index)