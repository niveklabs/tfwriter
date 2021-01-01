# aws_ses_domain_identity
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
module "aws_ses_domain_identity" {
  source = "./modules/aws/r/aws_ses_domain_identity"

  # domain - (required) is a type of string
  domain = null
}
```
[top](#index)
### Variables
```hcl
variable "domain" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_ses_domain_identity" "this" {
  domain = var.domain
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ses_domain_identity.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_domain_identity.this.id
}

output "verification_token" {
  description = "returns a string"
  value       = aws_ses_domain_identity.this.verification_token
}

output "this" {
  value = aws_ses_domain_identity.this
}
```
[top](#index)
