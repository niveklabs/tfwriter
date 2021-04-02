# aws_wafregional_regex_pattern_set

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
module "aws_wafregional_regex_pattern_set" {
  source = "./modules/aws/r/aws_wafregional_regex_pattern_set"

  # name - (required) is a type of string
  name = null
  # regex_pattern_strings - (optional) is a type of set of string
  regex_pattern_strings = []
}
```

[top](#index)

### Variables

```terraform
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

```terraform
resource "aws_wafregional_regex_pattern_set" "this" {
  name                  = var.name
  regex_pattern_strings = var.regex_pattern_strings
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_wafregional_regex_pattern_set.this.id
}

output "this" {
  value = aws_wafregional_regex_pattern_set.this
}
```

[top](#index)