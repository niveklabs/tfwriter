# checkpoint_management_service_compound_tcp

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
module "checkpoint_management_service_compound_tcp" {
  source = "./modules/checkpoint/r/checkpoint_management_service_compound_tcp"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # compound_service - (optional) is a type of string
  compound_service = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # keep_connections_open_after_policy_installation - (optional) is a type of bool
  keep_connections_open_after_policy_installation = null
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

variable "compound_service" {
  description = "(optional) - Compound service type."
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

variable "keep_connections_open_after_policy_installation" {
  description = "(optional) - Keep connections open after policy has been installed even if they are not allowed under the new policy. This overrides the settings in the Connection Persistence page. If you change this property, the change will not affect open connections, but only future connections."
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
resource "checkpoint_management_service_compound_tcp" "this" {
  color                                           = var.color
  comments                                        = var.comments
  compound_service                                = var.compound_service
  ignore_errors                                   = var.ignore_errors
  ignore_warnings                                 = var.ignore_warnings
  keep_connections_open_after_policy_installation = var.keep_connections_open_after_policy_installation
  name                                            = var.name
  tags                                            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_service_compound_tcp.this.id
}

output "this" {
  value = checkpoint_management_service_compound_tcp.this
}
```

[top](#index)