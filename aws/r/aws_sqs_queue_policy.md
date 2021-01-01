# aws_sqs_queue_policy
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
module "aws_sqs_queue_policy" {
  source = "./modules/aws/r/aws_sqs_queue_policy"

  # policy - (required) is a type of string
  policy = null
  # queue_url - (required) is a type of string
  queue_url = null
}
```
[top](#index)
### Variables
```hcl
variable "policy" {
  description = "(required)"
  type        = string
}

variable "queue_url" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_sqs_queue_policy" "this" {
  policy    = var.policy
  queue_url = var.queue_url
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_sqs_queue_policy.this.id
}

output "this" {
  value = aws_sqs_queue_policy.this
}
```
[top](#index)
