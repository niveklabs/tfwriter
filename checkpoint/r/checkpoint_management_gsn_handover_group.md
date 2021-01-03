# checkpoint_management_gsn_handover_group

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
module "checkpoint_management_gsn_handover_group" {
  source = "./modules/checkpoint/r/checkpoint_management_gsn_handover_group"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # enforce_gtp - (optional) is a type of bool
  enforce_gtp = null
  # gtp_rate - (optional) is a type of number
  gtp_rate = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # members - (optional) is a type of set of string
  members = []
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

variable "enforce_gtp" {
  description = "(optional) - Enable enforce GTP signal packet rate limit from this group."
  type        = bool
  default     = null
}

variable "gtp_rate" {
  description = "(optional) - Limit of the GTP rate in PDU/sec."
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

variable "members" {
  description = "(optional) - Collection of GSN handover group members identified by the name or UID."
  type        = set(string)
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
resource "checkpoint_management_gsn_handover_group" "this" {
  color           = var.color
  comments        = var.comments
  enforce_gtp     = var.enforce_gtp
  gtp_rate        = var.gtp_rate
  ignore_errors   = var.ignore_errors
  ignore_warnings = var.ignore_warnings
  members         = var.members
  name            = var.name
  tags            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_gsn_handover_group.this.id
}

output "this" {
  value = checkpoint_management_gsn_handover_group.this
}
```

[top](#index)