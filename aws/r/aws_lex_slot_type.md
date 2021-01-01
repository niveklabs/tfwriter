# aws_lex_slot_type

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
module "aws_lex_slot_type" {
  source = "./modules/aws/r/aws_lex_slot_type"

  # create_version - (optional) is a type of bool
  create_version = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # value_selection_strategy - (optional) is a type of string
  value_selection_strategy = null

  enumeration_value = [{
    synonyms = []
    value    = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "create_version" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "value_selection_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enumeration_value" {
  description = "nested mode: NestingSet, min items: 1, max items: 10000"
  type = set(object(
    {
      synonyms = set(string)
      value    = string
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_lex_slot_type" "this" {
  create_version           = var.create_version
  description              = var.description
  name                     = var.name
  value_selection_strategy = var.value_selection_strategy

  dynamic "enumeration_value" {
    for_each = var.enumeration_value
    content {
      synonyms = enumeration_value.value["synonyms"]
      value    = enumeration_value.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "checksum" {
  description = "returns a string"
  value       = aws_lex_slot_type.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = aws_lex_slot_type.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_lex_slot_type.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_lex_slot_type.this.last_updated_date
}

output "version" {
  description = "returns a string"
  value       = aws_lex_slot_type.this.version
}

output "this" {
  value = aws_lex_slot_type.this
}
```

[top](#index)