# okta_user_schema

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
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_user_schema" {
  source = "./modules/okta/r/okta_user_schema"

  # array_enum - (optional) is a type of list of string
  array_enum = []
  # array_type - (optional) is a type of string
  array_type = null
  # description - (optional) is a type of string
  description = null
  # enum - (optional) is a type of list of string
  enum = []
  # external_name - (optional) is a type of string
  external_name = null
  # external_namespace - (optional) is a type of string
  external_namespace = null
  # index - (required) is a type of string
  index = null
  # master - (optional) is a type of string
  master = null
  # max_length - (optional) is a type of number
  max_length = null
  # min_length - (optional) is a type of number
  min_length = null
  # pattern - (optional) is a type of string
  pattern = null
  # permissions - (optional) is a type of string
  permissions = null
  # required - (optional) is a type of bool
  required = null
  # scope - (optional) is a type of string
  scope = null
  # title - (required) is a type of string
  title = null
  # type - (required) is a type of string
  type = null
  # unique - (optional) is a type of string
  unique = null
  # user_type - (optional) is a type of string
  user_type = null

  array_one_of = [{
    const = null
    title = null
  }]

  one_of = [{
    const = null
    title = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "array_enum" {
  description = "(optional) - Custom Subschema enumerated value of a property of type array."
  type        = list(string)
  default     = null
}

variable "array_type" {
  description = "(optional) - Subschema array type: string, number, integer, reference. Type field must be an array."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Custom Subschema description"
  type        = string
  default     = null
}

variable "enum" {
  description = "(optional) - Custom Subschema enumerated value of the property. see: developer.okta.com/docs/api/resources/schemas#user-profile-schema-property-object"
  type        = list(string)
  default     = null
}

variable "external_name" {
  description = "(optional) - Subschema external name"
  type        = string
  default     = null
}

variable "external_namespace" {
  description = "(optional) - Subschema external namespace"
  type        = string
  default     = null
}

variable "index" {
  description = "(required) - Subschema unique string identifier"
  type        = string
}

variable "master" {
  description = "(optional) - SubSchema profile manager, if not set it will inherit its setting."
  type        = string
  default     = null
}

variable "max_length" {
  description = "(optional) - Subschema of type string maximum length"
  type        = number
  default     = null
}

variable "min_length" {
  description = "(optional) - Subschema of type string minimum length"
  type        = number
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

variable "scope" {
  description = "(optional)"
  type        = string
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

variable "unique" {
  description = "(optional) - Subschema unique restriction"
  type        = string
  default     = null
}

variable "user_type" {
  description = "(optional) - Custom subschema user type"
  type        = string
  default     = null
}

variable "array_one_of" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      const = string
      title = string
    }
  ))
  default = []
}

variable "one_of" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      const = string
      title = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_user_schema" "this" {
  array_enum         = var.array_enum
  array_type         = var.array_type
  description        = var.description
  enum               = var.enum
  external_name      = var.external_name
  external_namespace = var.external_namespace
  index              = var.index
  master             = var.master
  max_length         = var.max_length
  min_length         = var.min_length
  pattern            = var.pattern
  permissions        = var.permissions
  required           = var.required
  scope              = var.scope
  title              = var.title
  type               = var.type
  unique             = var.unique
  user_type          = var.user_type

  dynamic "array_one_of" {
    for_each = var.array_one_of
    content {
      const = array_one_of.value["const"]
      title = array_one_of.value["title"]
    }
  }

  dynamic "one_of" {
    for_each = var.one_of
    content {
      const = one_of.value["const"]
      title = one_of.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_user_schema.this.id
}

output "this" {
  value = okta_user_schema.this
}
```

[top](#index)