# aws_codeartifact_authorization_token
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
module "aws_codeartifact_authorization_token" {
  source = "./modules/aws/d/aws_codeartifact_authorization_token"

  # domain - (required) is a type of string
  domain = null
  # domain_owner - (optional) is a type of string
  domain_owner = null
  # duration_seconds - (optional) is a type of number
  duration_seconds = null
}
```
[top](#index)
### Variables
```hcl
variable "domain" {
  description = "(required)"
  type        = string
}

variable "domain_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}
```
[top](#index)

### Datasource
```hcl
data "aws_codeartifact_authorization_token" "this" {
  domain           = var.domain
  domain_owner     = var.domain_owner
  duration_seconds = var.duration_seconds
}
```
[top](#index)
### Outputs
```hcl
output "authorization_token" {
  description = "returns a string"
  value       = data.aws_codeartifact_authorization_token.this.authorization_token
}

output "domain_owner" {
  description = "returns a string"
  value       = data.aws_codeartifact_authorization_token.this.domain_owner
}

output "expiration" {
  description = "returns a string"
  value       = data.aws_codeartifact_authorization_token.this.expiration
}

output "id" {
  description = "returns a string"
  value       = data.aws_codeartifact_authorization_token.this.id
}

output "this" {
  value = aws_codeartifact_authorization_token.this
}
```
[top](#index)
