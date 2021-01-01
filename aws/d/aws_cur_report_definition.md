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
  source = "./modules/aws/d/aws_cur_report_definition"

  # report_name - (required) is a type of string
  report_name = null
}
```
[top](#index)
### Variables
```hcl
variable "report_name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_cur_report_definition" "this" {
  report_name = var.report_name
}
```
[top](#index)
### Outputs
```hcl
output "additional_artifacts" {
  description = "returns a set of string"
  value       = data.aws_cur_report_definition.this.additional_artifacts
}

output "additional_schema_elements" {
  description = "returns a set of string"
  value       = data.aws_cur_report_definition.this.additional_schema_elements
}

output "compression" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.compression
}

output "format" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.format
}

output "id" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.id
}

output "refresh_closed_reports" {
  description = "returns a bool"
  value       = data.aws_cur_report_definition.this.refresh_closed_reports
}

output "report_versioning" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.report_versioning
}

output "s3_bucket" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.s3_bucket
}

output "s3_prefix" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.s3_prefix
}

output "s3_region" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.s3_region
}

output "time_unit" {
  description = "returns a string"
  value       = data.aws_cur_report_definition.this.time_unit
}

output "this" {
  value = aws_cur_report_definition.this
}
```
[top](#index)
