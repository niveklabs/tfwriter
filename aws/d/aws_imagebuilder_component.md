# aws_imagebuilder_component

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_imagebuilder_component" {
  source = "./modules/aws/d/aws_imagebuilder_component"

  # arn - (required) is a type of string
  arn = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
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

### Datasource

```terraform
data "aws_imagebuilder_component" "this" {
  arn  = var.arn
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "change_description" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.change_description
}

output "data" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.data
}

output "date_created" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.date_created
}

output "description" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.description
}

output "encrypted" {
  description = "returns a bool"
  value       = data.aws_imagebuilder_component.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.kms_key_id
}

output "name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.name
}

output "owner" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.owner
}

output "platform" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.platform
}

output "supported_os_versions" {
  description = "returns a set of string"
  value       = data.aws_imagebuilder_component.this.supported_os_versions
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_imagebuilder_component.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.type
}

output "version" {
  description = "returns a string"
  value       = data.aws_imagebuilder_component.this.version
}

output "this" {
  value = aws_imagebuilder_component.this
}
```

[top](#index)