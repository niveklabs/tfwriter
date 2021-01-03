# checkpoint_management_service_icmp

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
module "checkpoint_management_service_icmp" {
  source = "./modules/checkpoint/r/checkpoint_management_service_icmp"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # icmp_code - (optional) is a type of number
  icmp_code = null
  # icmp_type - (optional) is a type of number
  icmp_type = null
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

variable "icmp_code" {
  description = "(optional) - As listed in: <a href=\"http://www.iana.org/assignments/icmp-parameters\" target=\"_blank\">RFC 792</a>."
  type        = number
  default     = null
}

variable "icmp_type" {
  description = "(optional) - As listed in: <a href=\"http://www.iana.org/assignments/icmp-parameters\" target=\"_blank\">RFC 792</a>."
  type        = number
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
resource "checkpoint_management_service_icmp" "this" {
  color                                           = var.color
  comments                                        = var.comments
  icmp_code                                       = var.icmp_code
  icmp_type                                       = var.icmp_type
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
  value       = checkpoint_management_service_icmp.this.id
}

output "this" {
  value = checkpoint_management_service_icmp.this
}
```

[top](#index)