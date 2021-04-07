# checkpoint_management_vpn_community_remote_access

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
module "checkpoint_management_vpn_community_remote_access" {
  source = "./modules/checkpoint/r/checkpoint_management_vpn_community_remote_access"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # gateways - (optional) is a type of set of string
  gateways = []
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
  # user_groups - (optional) is a type of set of string
  user_groups = []
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

variable "gateways" {
  description = "(optional) - Collection of Gateway objects identified by the name or UID."
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
  description = "(optional) - Object name."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "user_groups" {
  description = "(optional) - Collection of User group objects identified by the name or UID."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_vpn_community_remote_access" "this" {
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # gateways - (optional) is a type of set of string
  gateways = var.gateways
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (optional) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
  # user_groups - (optional) is a type of set of string
  user_groups = var.user_groups
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_vpn_community_remote_access.this.id
}

output "this" {
  value = checkpoint_management_vpn_community_remote_access.this
}
```

[top](#index)