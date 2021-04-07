# checkpoint_management_add_updatable_object

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
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_add_updatable_object" {
  source = "./modules/checkpoint/r/checkpoint_management_add_updatable_object"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # tags - (optional) is a type of set of string
  tags = []
  # uid_in_updatable_objects_repository - (optional) is a type of string
  uid_in_updatable_objects_repository = null
  # uri - (optional) is a type of string
  uri = null
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

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "uid_in_updatable_objects_repository" {
  description = "(optional) - Unique identifier of the updatable object in the Updatable Objects Repository."
  type        = string
  default     = null
}

variable "uri" {
  description = "(optional) - URI of the updatable object in the Updatable Objects Repository."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_add_updatable_object" "this" {
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # tags - (optional) is a type of set of string
  tags = var.tags
  # uid_in_updatable_objects_repository - (optional) is a type of string
  uid_in_updatable_objects_repository = var.uid_in_updatable_objects_repository
  # uri - (optional) is a type of string
  uri = var.uri
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_add_updatable_object.this.id
}

output "this" {
  value = checkpoint_management_add_updatable_object.this
}
```

[top](#index)