# aws_media_store_container

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_media_store_container" {
  source = "./modules/aws/r/aws_media_store_container"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
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

```terraform
resource "aws_media_store_container" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_media_store_container.this.arn
}

output "endpoint" {
  description = "returns a string"
  value       = aws_media_store_container.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_media_store_container.this.id
}

output "this" {
  value = aws_media_store_container.this
}
```

[top](#index)