# checkpoint_management_group_with_exclusion

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_group_with_exclusion" {
  source = "./modules/checkpoint/r/checkpoint_management_group_with_exclusion"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # except - (optional) is a type of string
  except = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # include - (optional) is a type of string
  include = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "except" {
  description = "(optional) - Name or UID of an object which the group excludes."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "include" {
  description = "(optional) - Name or UID of an object which the group includes."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_group_with_exclusion" "this" {
  color           = var.color
  comments        = var.comments
  except          = var.except
  ignore_errors   = var.ignore_errors
  ignore_warnings = var.ignore_warnings
  include         = var.include
  name            = var.name
  tags            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_group_with_exclusion.this.id
}

output "this" {
  value = checkpoint_management_group_with_exclusion.this
}
```

[top](#index)