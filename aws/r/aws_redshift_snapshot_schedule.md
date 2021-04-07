# aws_redshift_snapshot_schedule

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
module "aws_redshift_snapshot_schedule" {
  source = "./modules/aws/r/aws_redshift_snapshot_schedule"

  # definitions - (required) is a type of set of string
  definitions = []
  # description - (optional) is a type of string
  description = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # identifier - (optional) is a type of string
  identifier = null
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "definitions" {
  description = "(required)"
  type        = set(string)
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier_prefix" {
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
resource "aws_redshift_snapshot_schedule" "this" {
  # definitions - (required) is a type of set of string
  definitions = var.definitions
  # description - (optional) is a type of string
  description = var.description
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # identifier - (optional) is a type of string
  identifier = var.identifier
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = var.identifier_prefix
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_redshift_snapshot_schedule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_redshift_snapshot_schedule.this.id
}

output "identifier" {
  description = "returns a string"
  value       = aws_redshift_snapshot_schedule.this.identifier
}

output "identifier_prefix" {
  description = "returns a string"
  value       = aws_redshift_snapshot_schedule.this.identifier_prefix
}

output "this" {
  value = aws_redshift_snapshot_schedule.this
}
```

[top](#index)