# checkpoint_management_service_other

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
module "checkpoint_management_service_other" {
  source = "./modules/checkpoint/r/checkpoint_management_service_other"

  # accept_replies - (optional) is a type of bool
  accept_replies = null
  # action - (optional) is a type of string
  action = null
  # aggressive_aging - (optional) is a type of map of string
  aggressive_aging = {}
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ip_protocol - (optional) is a type of number
  ip_protocol = null
  # keep_connections_open_after_policy_installation - (optional) is a type of bool
  keep_connections_open_after_policy_installation = null
  # match - (optional) is a type of string
  match = null
  # match_for_any - (optional) is a type of bool
  match_for_any = null
  # name - (required) is a type of string
  name = null
  # override_default_settings - (optional) is a type of bool
  override_default_settings = null
  # session_timeout - (optional) is a type of number
  session_timeout = null
  # sync_connections_on_cluster - (optional) is a type of bool
  sync_connections_on_cluster = null
  # tags - (optional) is a type of set of string
  tags = []
  # use_default_session_timeout - (optional) is a type of bool
  use_default_session_timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "accept_replies" {
  description = "(optional) - Specifies whether Other Service replies are to be accepted."
  type        = bool
  default     = null
}

variable "action" {
  description = "(optional) - Contains an INSPECT expression that defines the action to take if a rule containing this service is matched. Example: set r_mhandler &open_ssl_handler sets a handler on the connection."
  type        = string
  default     = null
}

variable "aggressive_aging" {
  description = "(optional) - Sets short (aggressive) timeouts for idle connections."
  type        = map(string)
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

variable "ip_protocol" {
  description = "(optional) - IP protocol number."
  type        = number
  default     = null
}

variable "keep_connections_open_after_policy_installation" {
  description = "(optional) - Keep connections open after policy has been installed even if they are not allowed under the new policy. This overrides the settings in the Connection Persistence page. If you change this property, the change will not affect open connections, but only future connections."
  type        = bool
  default     = null
}

variable "match" {
  description = "(optional) - Contains an INSPECT expression that defines the matching criteria. The connection is examined against the expression during the first packet. Example: tcp, dport = 21, direction = 0 matches incoming FTP control connections."
  type        = string
  default     = null
}

variable "match_for_any" {
  description = "(optional) - Indicates whether this service is used when 'Any' is set as the rule's service and there are several service objects with the same source port and protocol."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "override_default_settings" {
  description = "(optional) - Indicates whether this service is a Data Domain service which has been overridden."
  type        = bool
  default     = null
}

variable "session_timeout" {
  description = "(optional) - Time (in seconds) before the session times out."
  type        = number
  default     = null
}

variable "sync_connections_on_cluster" {
  description = "(optional) - Enables state-synchronized High Availability or Load Sharing on a ClusterXL or OPSEC-certified cluster."
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "use_default_session_timeout" {
  description = "(optional) - Use default virtual session timeout."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_service_other" "this" {
  accept_replies                                  = var.accept_replies
  action                                          = var.action
  aggressive_aging                                = var.aggressive_aging
  color                                           = var.color
  comments                                        = var.comments
  ignore_errors                                   = var.ignore_errors
  ignore_warnings                                 = var.ignore_warnings
  ip_protocol                                     = var.ip_protocol
  keep_connections_open_after_policy_installation = var.keep_connections_open_after_policy_installation
  match                                           = var.match
  match_for_any                                   = var.match_for_any
  name                                            = var.name
  override_default_settings                       = var.override_default_settings
  session_timeout                                 = var.session_timeout
  sync_connections_on_cluster                     = var.sync_connections_on_cluster
  tags                                            = var.tags
  use_default_session_timeout                     = var.use_default_session_timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_service_other.this.id
}

output "this" {
  value = checkpoint_management_service_other.this
}
```

[top](#index)