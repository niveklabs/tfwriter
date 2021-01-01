# aws_sfn_activity
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
module "aws_sfn_activity" {
  source = "./modules/aws/r/aws_sfn_activity"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "name" {
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
resource "aws_sfn_activity" "this" {
  name = var.name
  tags = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "creation_date" {
  description = "returns a string"
  value       = aws_sfn_activity.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = aws_sfn_activity.this.id
}

output "this" {
  value = aws_sfn_activity.this
}
```
[top](#index)
