# okta_user_base_schema

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_user_base_schema" {
  source = "./modules/okta/r/okta_user_base_schema"

  # index - (required) is a type of string
  index = null
  # master - (optional) is a type of string
  master = null
  # pattern - (optional) is a type of string
  pattern = null
  # permissions - (optional) is a type of string
  permissions = null
  # required - (optional) is a type of bool
  required = null
  # title - (required) is a type of string
  title = null
  # type - (required) is a type of string
  type = null
  # user_type - (optional) is a type of string
  user_type = null
}
```

[top](#index)

### Variables

```terraform
variable "index" {
  description = "(required) - Subschema unique string identifier"
  type        = string
}

variable "master" {
  description = "(optional) - SubSchema profile manager, if not set it will inherit its setting."
  type        = string
  default     = null
}

variable "pattern" {
  description = "(optional) - The validation pattern to use for the subschema. Must be in form of '.+', or '[<pattern>]+' if present.'"
  type        = string
  default     = null
}

variable "permissions" {
  description = "(optional) - SubSchema permissions: HIDE, READ_ONLY, or READ_WRITE."
  type        = string
  default     = null
}

variable "required" {
  description = "(optional) - Whether the subschema is required"
  type        = bool
  default     = null
}

variable "title" {
  description = "(required) - Subschema title (display name)"
  type        = string
}

variable "type" {
  description = "(required) - Subschema type: string, boolean, number, integer, array, or object"
  type        = string
}

variable "user_type" {
  description = "(optional) - Custom subschema user type"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_user_base_schema" "this" {
  # index - (required) is a type of string
  index = var.index
  # master - (optional) is a type of string
  master = var.master
  # pattern - (optional) is a type of string
  pattern = var.pattern
  # permissions - (optional) is a type of string
  permissions = var.permissions
  # required - (optional) is a type of bool
  required = var.required
  # title - (required) is a type of string
  title = var.title
  # type - (required) is a type of string
  type = var.type
  # user_type - (optional) is a type of string
  user_type = var.user_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_user_base_schema.this.id
}

output "this" {
  value = okta_user_base_schema.this
}
```

[top](#index)