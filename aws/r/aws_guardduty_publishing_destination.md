# aws_guardduty_publishing_destination

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
module "aws_guardduty_publishing_destination" {
  source = "./modules/aws/r/aws_guardduty_publishing_destination"

  # destination_arn - (required) is a type of string
  destination_arn = null
  # destination_type - (optional) is a type of string
  destination_type = null
  # detector_id - (required) is a type of string
  detector_id = null
  # kms_key_arn - (required) is a type of string
  kms_key_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "destination_arn" {
  description = "(required)"
  type        = string
}

variable "destination_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "kms_key_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_guardduty_publishing_destination" "this" {
  destination_arn  = var.destination_arn
  destination_type = var.destination_type
  detector_id      = var.detector_id
  kms_key_arn      = var.kms_key_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_guardduty_publishing_destination.this.id
}

output "this" {
  value = aws_guardduty_publishing_destination.this
}
```

[top](#index)