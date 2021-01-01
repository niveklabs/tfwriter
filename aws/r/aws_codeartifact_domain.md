# aws_codeartifact_domain
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
module "aws_codeartifact_domain" {
  source = "./modules/aws/r/aws_codeartifact_domain"

  # domain - (required) is a type of string
  domain = null
  # encryption_key - (required) is a type of string
  encryption_key = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "domain" {
  description = "(required)"
  type        = string
}

variable "encryption_key" {
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
```hcl
resource "aws_codeartifact_domain" "this" {
  domain         = var.domain
  encryption_key = var.encryption_key
  tags           = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_codeartifact_domain.this.arn
}

output "asset_size_bytes" {
  description = "returns a number"
  value       = aws_codeartifact_domain.this.asset_size_bytes
}

output "created_time" {
  description = "returns a string"
  value       = aws_codeartifact_domain.this.created_time
}

output "id" {
  description = "returns a string"
  value       = aws_codeartifact_domain.this.id
}

output "owner" {
  description = "returns a string"
  value       = aws_codeartifact_domain.this.owner
}

output "repository_count" {
  description = "returns a number"
  value       = aws_codeartifact_domain.this.repository_count
}

output "this" {
  value = aws_codeartifact_domain.this
}
```
[top](#index)
