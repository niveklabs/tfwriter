# aws_ssm_maintenance_window

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ssm_maintenance_window" {
  source = "./modules/aws/r/aws_ssm_maintenance_window"

  # allow_unassociated_targets - (optional) is a type of bool
  allow_unassociated_targets = null
  # cutoff - (required) is a type of number
  cutoff = null
  # description - (optional) is a type of string
  description = null
  # duration - (required) is a type of number
  duration = null
  # enabled - (optional) is a type of bool
  enabled = null
  # end_date - (optional) is a type of string
  end_date = null
  # name - (required) is a type of string
  name = null
  # schedule - (required) is a type of string
  schedule = null
  # schedule_offset - (optional) is a type of number
  schedule_offset = null
  # schedule_timezone - (optional) is a type of string
  schedule_timezone = null
  # start_date - (optional) is a type of string
  start_date = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "allow_unassociated_targets" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cutoff" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration" {
  description = "(required)"
  type        = number
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "end_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schedule" {
  description = "(required)"
  type        = string
}

variable "schedule_offset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "schedule_timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_date" {
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
resource "aws_ssm_maintenance_window" "this" {
  allow_unassociated_targets = var.allow_unassociated_targets
  cutoff                     = var.cutoff
  description                = var.description
  duration                   = var.duration
  enabled                    = var.enabled
  end_date                   = var.end_date
  name                       = var.name
  schedule                   = var.schedule
  schedule_offset            = var.schedule_offset
  schedule_timezone          = var.schedule_timezone
  start_date                 = var.start_date
  tags                       = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssm_maintenance_window.this.id
}

output "this" {
  value = aws_ssm_maintenance_window.this
}
```

[top](#index)