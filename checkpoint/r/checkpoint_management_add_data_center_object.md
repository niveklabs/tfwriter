# checkpoint_management_add_data_center_object

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
module "checkpoint_management_add_data_center_object" {
  source = "./modules/checkpoint/r/checkpoint_management_add_data_center_object"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # data_center_name - (optional) is a type of string
  data_center_name = null
  # data_center_uid - (optional) is a type of string
  data_center_uid = null
  # groups - (optional) is a type of set of string
  groups = []
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
  # uid_in_data_center - (optional) is a type of string
  uid_in_data_center = null
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

variable "data_center_name" {
  description = "(optional) - Name of the Data Center Server the object is in."
  type        = string
  default     = null
}

variable "data_center_uid" {
  description = "(optional) - Unique identifier of the Data Center Server the object is in."
  type        = string
  default     = null
}

variable "groups" {
  description = "(optional) - Collection of group identifiers."
  type        = set(string)
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

variable "name" {
  description = "(optional) - Override default name on data-center."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "uid_in_data_center" {
  description = "(optional) - Unique identifier of the object in the Data Center Server."
  type        = string
  default     = null
}

variable "uri" {
  description = "(optional) - URI of the object in the Data Center Server."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_add_data_center_object" "this" {
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # data_center_name - (optional) is a type of string
  data_center_name = var.data_center_name
  # data_center_uid - (optional) is a type of string
  data_center_uid = var.data_center_uid
  # groups - (optional) is a type of set of string
  groups = var.groups
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (optional) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
  # uid_in_data_center - (optional) is a type of string
  uid_in_data_center = var.uid_in_data_center
  # uri - (optional) is a type of string
  uri = var.uri
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_add_data_center_object.this.id
}

output "this" {
  value = checkpoint_management_add_data_center_object.this
}
```

[top](#index)