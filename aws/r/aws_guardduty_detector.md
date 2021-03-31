# aws_guardduty_detector

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_guardduty_detector" {
  source = "./modules/aws/r/aws_guardduty_detector"

  # enable - (optional) is a type of bool
  enable = null
  # finding_publishing_frequency - (optional) is a type of string
  finding_publishing_frequency = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "finding_publishing_frequency" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "aws_guardduty_detector" "this" {
  enable                       = var.enable
  finding_publishing_frequency = var.finding_publishing_frequency
  tags                         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = aws_guardduty_detector.this.account_id
}

output "arn" {
  description = "returns a string"
  value       = aws_guardduty_detector.this.arn
}

output "finding_publishing_frequency" {
  description = "returns a string"
  value       = aws_guardduty_detector.this.finding_publishing_frequency
}

output "id" {
  description = "returns a string"
  value       = aws_guardduty_detector.this.id
}

output "this" {
  value = aws_guardduty_detector.this
}
```

[top](#index)