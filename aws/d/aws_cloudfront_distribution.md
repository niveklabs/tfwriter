# aws_cloudfront_distribution
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
module "aws_cloudfront_distribution" {
  source = "./modules/aws/d/aws_cloudfront_distribution"

  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```
[top](#index)

### Datasource
```hcl
data "aws_cloudfront_distribution" "this" {
  tags = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.arn
}

output "domain_name" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.domain_name
}

output "enabled" {
  description = "returns a bool"
  value       = data.aws_cloudfront_distribution.this.enabled
}

output "etag" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.etag
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.id
}

output "in_progress_validation_batches" {
  description = "returns a number"
  value       = data.aws_cloudfront_distribution.this.in_progress_validation_batches
}

output "last_modified_time" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.last_modified_time
}

output "status" {
  description = "returns a string"
  value       = data.aws_cloudfront_distribution.this.status
}

output "this" {
  value = aws_cloudfront_distribution.this
}
```
[top](#index)
