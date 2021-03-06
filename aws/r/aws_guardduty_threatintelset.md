# aws_guardduty_threatintelset

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
module "aws_guardduty_threatintelset" {
  source = "./modules/aws/r/aws_guardduty_threatintelset"

  # activate - (required) is a type of bool
  activate = null
  # detector_id - (required) is a type of string
  detector_id = null
  # format - (required) is a type of string
  format = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "activate" {
  description = "(required)"
  type        = bool
}

variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "format" {
  description = "(required)"
  type        = string
}

variable "location" {
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
resource "aws_guardduty_threatintelset" "this" {
  # activate - (required) is a type of bool
  activate = var.activate
  # detector_id - (required) is a type of string
  detector_id = var.detector_id
  # format - (required) is a type of string
  format = var.format
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_guardduty_threatintelset.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_guardduty_threatintelset.this.id
}

output "this" {
  value = aws_guardduty_threatintelset.this
}
```

[top](#index)