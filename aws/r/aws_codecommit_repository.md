# aws_codecommit_repository
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
module "aws_codecommit_repository" {
  source = "./modules/aws/r/aws_codecommit_repository"

  # default_branch - (optional) is a type of string
  default_branch = null
  # description - (optional) is a type of string
  description = null
  # repository_name - (required) is a type of string
  repository_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "default_branch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository_name" {
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
resource "aws_codecommit_repository" "this" {
  default_branch  = var.default_branch
  description     = var.description
  repository_name = var.repository_name
  tags            = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_codecommit_repository.this.arn
}

output "clone_url_http" {
  description = "returns a string"
  value       = aws_codecommit_repository.this.clone_url_http
}

output "clone_url_ssh" {
  description = "returns a string"
  value       = aws_codecommit_repository.this.clone_url_ssh
}

output "id" {
  description = "returns a string"
  value       = aws_codecommit_repository.this.id
}

output "repository_id" {
  description = "returns a string"
  value       = aws_codecommit_repository.this.repository_id
}

output "this" {
  value = aws_codecommit_repository.this
}
```
[top](#index)
