# aws_glue_user_defined_function

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_glue_user_defined_function" {
  source = "./modules/aws/r/aws_glue_user_defined_function"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # class_name - (required) is a type of string
  class_name = null
  # database_name - (required) is a type of string
  database_name = null
  # name - (required) is a type of string
  name = null
  # owner_name - (required) is a type of string
  owner_name = null
  # owner_type - (required) is a type of string
  owner_type = null

  resource_uris = [{
    resource_type = null
    uri           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "class_name" {
  description = "(required)"
  type        = string
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_name" {
  description = "(required)"
  type        = string
}

variable "owner_type" {
  description = "(required)"
  type        = string
}

variable "resource_uris" {
  description = "nested block: NestingSet, min items: 0, max items: 1000"
  type = set(object(
    {
      resource_type = string
      uri           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_user_defined_function" "this" {
  catalog_id    = var.catalog_id
  class_name    = var.class_name
  database_name = var.database_name
  name          = var.name
  owner_name    = var.owner_name
  owner_type    = var.owner_type

  dynamic "resource_uris" {
    for_each = var.resource_uris
    content {
      resource_type = resource_uris.value["resource_type"]
      uri           = resource_uris.value["uri"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_user_defined_function.this.arn
}

output "create_time" {
  description = "returns a string"
  value       = aws_glue_user_defined_function.this.create_time
}

output "id" {
  description = "returns a string"
  value       = aws_glue_user_defined_function.this.id
}

output "this" {
  value = aws_glue_user_defined_function.this
}
```

[top](#index)