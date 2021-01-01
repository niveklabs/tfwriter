# aws_networkfirewall_resource_policy
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
module "aws_networkfirewall_resource_policy" {
  source = "./modules/aws/r/aws_networkfirewall_resource_policy"

  # policy - (required) is a type of string
  policy = null
  # resource_arn - (required) is a type of string
  resource_arn = null
}
```
[top](#index)
### Variables
```hcl
variable "policy" {
  description = "(required)"
  type        = string
}

variable "resource_arn" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_networkfirewall_resource_policy" "this" {
  policy       = var.policy
  resource_arn = var.resource_arn
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_networkfirewall_resource_policy.this.id
}

output "this" {
  value = aws_networkfirewall_resource_policy.this
}
```
[top](#index)
