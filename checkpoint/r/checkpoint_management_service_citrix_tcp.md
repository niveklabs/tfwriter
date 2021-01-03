# checkpoint_management_service_citrix_tcp

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
module "checkpoint_management_service_citrix_tcp" {
  source = "./modules/checkpoint/r/checkpoint_management_service_citrix_tcp"

  # application - (optional) is a type of string
  application = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "application" {
  description = "(optional) - Citrix application name."
  type        = string
  default     = null
}

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
resource "checkpoint_management_service_citrix_tcp" "this" {
  application     = var.application
  color           = var.color
  comments        = var.comments
  ignore_errors   = var.ignore_errors
  ignore_warnings = var.ignore_warnings
  name            = var.name
  tags            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_service_citrix_tcp.this.id
}

output "this" {
  value = checkpoint_management_service_citrix_tcp.this
}
```

[top](#index)