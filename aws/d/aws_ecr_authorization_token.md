# aws_ecr_authorization_token
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
module "aws_ecr_authorization_token" {
  source = "./modules/aws/d/aws_ecr_authorization_token"

  # registry_id - (optional) is a type of string
  registry_id = null
}
```
[top](#index)
### Variables
```hcl
variable "registry_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```
[top](#index)

### Datasource
```hcl
data "aws_ecr_authorization_token" "this" {
  registry_id = var.registry_id
}
```
[top](#index)
### Outputs
```hcl
output "authorization_token" {
  description = "returns a string"
  value       = data.aws_ecr_authorization_token.this.authorization_token
  sensitive   = true
}

output "expires_at" {
  description = "returns a string"
  value       = data.aws_ecr_authorization_token.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = data.aws_ecr_authorization_token.this.id
}

output "password" {
  description = "returns a string"
  value       = data.aws_ecr_authorization_token.this.password
  sensitive   = true
}

output "proxy_endpoint" {
  description = "returns a string"
  value       = data.aws_ecr_authorization_token.this.proxy_endpoint
}

output "user_name" {
  description = "returns a string"
  value       = data.aws_ecr_authorization_token.this.user_name
}

output "this" {
  value = aws_ecr_authorization_token.this
}
```
[top](#index)
