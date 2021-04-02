# aws_db_option_group

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
module "aws_db_option_group" {
  source = "./modules/aws/r/aws_db_option_group"

  # engine_name - (required) is a type of string
  engine_name = null
  # major_engine_version - (required) is a type of string
  major_engine_version = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # option_group_description - (optional) is a type of string
  option_group_description = null
  # tags - (optional) is a type of map of string
  tags = {}

  option = [{
    db_security_group_memberships = []
    option_name                   = null
    option_settings = [{
      name  = null
      value = null
    }]
    port                           = null
    version                        = null
    vpc_security_group_memberships = []
  }]

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "engine_name" {
  description = "(required)"
  type        = string
}

variable "major_engine_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "option_group_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "option" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      db_security_group_memberships = set(string)
      option_name                   = string
      option_settings = set(object(
        {
          name  = string
          value = string
        }
      ))
      port                           = number
      version                        = string
      vpc_security_group_memberships = set(string)
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
resource "aws_db_option_group" "this" {
  engine_name              = var.engine_name
  major_engine_version     = var.major_engine_version
  name                     = var.name
  name_prefix              = var.name_prefix
  option_group_description = var.option_group_description
  tags                     = var.tags

  dynamic "option" {
    for_each = var.option
    content {
      db_security_group_memberships  = option.value["db_security_group_memberships"]
      option_name                    = option.value["option_name"]
      port                           = option.value["port"]
      version                        = option.value["version"]
      vpc_security_group_memberships = option.value["vpc_security_group_memberships"]

      dynamic "option_settings" {
        for_each = option.value.option_settings
        content {
          name  = option_settings.value["name"]
          value = option_settings.value["value"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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
  value       = aws_db_option_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_db_option_group.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_db_option_group.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_db_option_group.this.name_prefix
}

output "this" {
  value = aws_db_option_group.this
}
```

[top](#index)