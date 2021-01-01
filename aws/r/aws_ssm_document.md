# aws_ssm_document

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
module "aws_ssm_document" {
  source = "./modules/aws/r/aws_ssm_document"

  # content - (required) is a type of string
  content = null
  # document_format - (optional) is a type of string
  document_format = null
  # document_type - (required) is a type of string
  document_type = null
  # name - (required) is a type of string
  name = null
  # permissions - (optional) is a type of map of string
  permissions = {}
  # tags - (optional) is a type of map of string
  tags = {}
  # target_type - (optional) is a type of string
  target_type = null

  attachments_source = [{
    key    = null
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```hcl
variable "content" {
  description = "(required)"
  type        = string
}

variable "document_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "document_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attachments_source" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key    = string
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_ssm_document" "this" {
  content         = var.content
  document_format = var.document_format
  document_type   = var.document_type
  name            = var.name
  permissions     = var.permissions
  tags            = var.tags
  target_type     = var.target_type

  dynamic "attachments_source" {
    for_each = var.attachments_source
    content {
      key    = attachments_source.value["key"]
      name   = attachments_source.value["name"]
      values = attachments_source.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ssm_document.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_ssm_document.this.created_date
}

output "default_version" {
  description = "returns a string"
  value       = aws_ssm_document.this.default_version
}

output "description" {
  description = "returns a string"
  value       = aws_ssm_document.this.description
}

output "document_version" {
  description = "returns a string"
  value       = aws_ssm_document.this.document_version
}

output "hash" {
  description = "returns a string"
  value       = aws_ssm_document.this.hash
}

output "hash_type" {
  description = "returns a string"
  value       = aws_ssm_document.this.hash_type
}

output "id" {
  description = "returns a string"
  value       = aws_ssm_document.this.id
}

output "latest_version" {
  description = "returns a string"
  value       = aws_ssm_document.this.latest_version
}

output "owner" {
  description = "returns a string"
  value       = aws_ssm_document.this.owner
}

output "parameter" {
  description = "returns a list of object"
  value       = aws_ssm_document.this.parameter
}

output "platform_types" {
  description = "returns a list of string"
  value       = aws_ssm_document.this.platform_types
}

output "schema_version" {
  description = "returns a string"
  value       = aws_ssm_document.this.schema_version
}

output "status" {
  description = "returns a string"
  value       = aws_ssm_document.this.status
}

output "this" {
  value = aws_ssm_document.this
}
```

[top](#index)