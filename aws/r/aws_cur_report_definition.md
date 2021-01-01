# aws_cur_report_definition

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_cur_report_definition" {
  source = "./modules/aws/r/aws_cur_report_definition"

  # additional_artifacts - (optional) is a type of set of string
  additional_artifacts = []
  # additional_schema_elements - (required) is a type of set of string
  additional_schema_elements = []
  # compression - (required) is a type of string
  compression = null
  # format - (required) is a type of string
  format = null
  # refresh_closed_reports - (optional) is a type of bool
  refresh_closed_reports = null
  # report_name - (required) is a type of string
  report_name = null
  # report_versioning - (optional) is a type of string
  report_versioning = null
  # s3_bucket - (required) is a type of string
  s3_bucket = null
  # s3_prefix - (optional) is a type of string
  s3_prefix = null
  # s3_region - (required) is a type of string
  s3_region = null
  # time_unit - (required) is a type of string
  time_unit = null
}
```

[top](#index)

### Variables

```hcl
variable "additional_artifacts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "additional_schema_elements" {
  description = "(required)"
  type        = set(string)
}

variable "compression" {
  description = "(required)"
  type        = string
}

variable "format" {
  description = "(required)"
  type        = string
}

variable "refresh_closed_reports" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "report_name" {
  description = "(required)"
  type        = string
}

variable "report_versioning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_bucket" {
  description = "(required)"
  type        = string
}

variable "s3_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_region" {
  description = "(required)"
  type        = string
}

variable "time_unit" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_cur_report_definition" "this" {
  additional_artifacts       = var.additional_artifacts
  additional_schema_elements = var.additional_schema_elements
  compression                = var.compression
  format                     = var.format
  refresh_closed_reports     = var.refresh_closed_reports
  report_name                = var.report_name
  report_versioning          = var.report_versioning
  s3_bucket                  = var.s3_bucket
  s3_prefix                  = var.s3_prefix
  s3_region                  = var.s3_region
  time_unit                  = var.time_unit
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_cur_report_definition.this.id
}

output "this" {
  value = aws_cur_report_definition.this
}
```

[top](#index)