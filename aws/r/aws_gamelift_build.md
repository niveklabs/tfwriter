# aws_gamelift_build

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
module "aws_gamelift_build" {
  source = "./modules/aws/r/aws_gamelift_build"

  # name - (required) is a type of string
  name = null
  # operating_system - (required) is a type of string
  operating_system = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (optional) is a type of string
  version = null

  storage_location = [{
    bucket   = null
    key      = null
    role_arn = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "operating_system" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_location" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      bucket   = string
      key      = string
      role_arn = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_gamelift_build" "this" {
  # name - (required) is a type of string
  name = var.name
  # operating_system - (required) is a type of string
  operating_system = var.operating_system
  # tags - (optional) is a type of map of string
  tags = var.tags
  # version - (optional) is a type of string
  version = var.version

  dynamic "storage_location" {
    for_each = var.storage_location
    content {
      # bucket - (required) is a type of string
      bucket = storage_location.value["bucket"]
      # key - (required) is a type of string
      key = storage_location.value["key"]
      # role_arn - (required) is a type of string
      role_arn = storage_location.value["role_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_gamelift_build.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_gamelift_build.this.id
}

output "this" {
  value = aws_gamelift_build.this
}
```

[top](#index)