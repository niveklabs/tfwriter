# aws_ecr_repository

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
module "aws_ecr_repository" {
  source = "./modules/aws/r/aws_ecr_repository"

  # image_tag_mutability - (optional) is a type of string
  image_tag_mutability = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  encryption_configuration = [{
    encryption_type = null
    kms_key         = null
  }]

  image_scanning_configuration = [{
    scan_on_push = null
  }]

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "image_tag_mutability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "encryption_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      encryption_type = string
      kms_key         = string
    }
  ))
  default = []
}

variable "image_scanning_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      scan_on_push = bool
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ecr_repository" "this" {
  # image_tag_mutability - (optional) is a type of string
  image_tag_mutability = var.image_tag_mutability
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "encryption_configuration" {
    for_each = var.encryption_configuration
    content {
      # encryption_type - (optional) is a type of string
      encryption_type = encryption_configuration.value["encryption_type"]
      # kms_key - (optional) is a type of string
      kms_key = encryption_configuration.value["kms_key"]
    }
  }

  dynamic "image_scanning_configuration" {
    for_each = var.image_scanning_configuration
    content {
      # scan_on_push - (required) is a type of bool
      scan_on_push = image_scanning_configuration.value["scan_on_push"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ecr_repository.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ecr_repository.this.id
}

output "registry_id" {
  description = "returns a string"
  value       = aws_ecr_repository.this.registry_id
}

output "repository_url" {
  description = "returns a string"
  value       = aws_ecr_repository.this.repository_url
}

output "this" {
  value = aws_ecr_repository.this
}
```

[top](#index)