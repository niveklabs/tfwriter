# aws_transfer_ssh_key
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
module "aws_transfer_ssh_key" {
  source = "./modules/aws/r/aws_transfer_ssh_key"

  # body - (required) is a type of string
  body = null
  # server_id - (required) is a type of string
  server_id = null
  # user_name - (required) is a type of string
  user_name = null
}
```
[top](#index)
### Variables
```hcl
variable "body" {
  description = "(required)"
  type        = string
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "user_name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_transfer_ssh_key" "this" {
  body      = var.body
  server_id = var.server_id
  user_name = var.user_name
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_transfer_ssh_key.this.id
}

output "this" {
  value = aws_transfer_ssh_key.this
}
```
[top](#index)
