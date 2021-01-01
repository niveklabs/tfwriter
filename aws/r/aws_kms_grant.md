# aws_kms_grant
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
module "aws_kms_grant" {
  source = "./modules/aws/r/aws_kms_grant"

  # grant_creation_tokens - (optional) is a type of set of string
  grant_creation_tokens = []
  # grantee_principal - (required) is a type of string
  grantee_principal = null
  # key_id - (required) is a type of string
  key_id = null
  # name - (optional) is a type of string
  name = null
  # operations - (required) is a type of set of string
  operations = []
  # retire_on_delete - (optional) is a type of bool
  retire_on_delete = null
  # retiring_principal - (optional) is a type of string
  retiring_principal = null

  constraints = [{
    encryption_context_equals = {}
    encryption_context_subset = {}
  }]
}
```
[top](#index)
### Variables
```hcl
variable "grant_creation_tokens" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "grantee_principal" {
  description = "(required)"
  type        = string
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operations" {
  description = "(required)"
  type        = set(string)
}

variable "retire_on_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "retiring_principal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "constraints" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      encryption_context_equals = map(string)
      encryption_context_subset = map(string)
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_kms_grant" "this" {
  grant_creation_tokens = var.grant_creation_tokens
  grantee_principal     = var.grantee_principal
  key_id                = var.key_id
  name                  = var.name
  operations            = var.operations
  retire_on_delete      = var.retire_on_delete
  retiring_principal    = var.retiring_principal

  dynamic "constraints" {
    for_each = var.constraints
    content {
      encryption_context_equals = constraints.value["encryption_context_equals"]
      encryption_context_subset = constraints.value["encryption_context_subset"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "grant_id" {
  description = "returns a string"
  value       = aws_kms_grant.this.grant_id
}

output "grant_token" {
  description = "returns a string"
  value       = aws_kms_grant.this.grant_token
}

output "id" {
  description = "returns a string"
  value       = aws_kms_grant.this.id
}

output "this" {
  value = aws_kms_grant.this
}
```
[top](#index)
