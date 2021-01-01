# aws_securityhub_standards_subscription
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
module "aws_securityhub_standards_subscription" {
  source = "./modules/aws/r/aws_securityhub_standards_subscription"

  # standards_arn - (required) is a type of string
  standards_arn = null
}
```
[top](#index)
### Variables
```hcl
variable "standards_arn" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_securityhub_standards_subscription" "this" {
  standards_arn = var.standards_arn
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_securityhub_standards_subscription.this.id
}

output "this" {
  value = aws_securityhub_standards_subscription.this
}
```
[top](#index)
