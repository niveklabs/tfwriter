# aws_athena_database
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
module "aws_athena_database" {
  source = "./modules/aws/r/aws_athena_database"

  # bucket - (required) is a type of string
  bucket = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null

  encryption_configuration = [{
    encryption_option = null
    kms_key           = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "encryption_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      encryption_option = string
      kms_key           = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_athena_database" "this" {
  bucket        = var.bucket
  force_destroy = var.force_destroy
  name          = var.name

  dynamic "encryption_configuration" {
    for_each = var.encryption_configuration
    content {
      encryption_option = encryption_configuration.value["encryption_option"]
      kms_key           = encryption_configuration.value["kms_key"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_athena_database.this.id
}

output "this" {
  value = aws_athena_database.this
}
```
[top](#index)
