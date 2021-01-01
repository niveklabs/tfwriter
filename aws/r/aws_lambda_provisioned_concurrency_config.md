# aws_lambda_provisioned_concurrency_config
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
module "aws_lambda_provisioned_concurrency_config" {
  source = "./modules/aws/r/aws_lambda_provisioned_concurrency_config"

  # function_name - (required) is a type of string
  function_name = null
  # provisioned_concurrent_executions - (required) is a type of number
  provisioned_concurrent_executions = null
  # qualifier - (required) is a type of string
  qualifier = null

  timeouts = [{
    create = null
    update = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "function_name" {
  description = "(required)"
  type        = string
}

variable "provisioned_concurrent_executions" {
  description = "(required)"
  type        = number
}

variable "qualifier" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_lambda_provisioned_concurrency_config" "this" {
  function_name                     = var.function_name
  provisioned_concurrent_executions = var.provisioned_concurrent_executions
  qualifier                         = var.qualifier

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_lambda_provisioned_concurrency_config.this.id
}

output "this" {
  value = aws_lambda_provisioned_concurrency_config.this
}
```
[top](#index)
