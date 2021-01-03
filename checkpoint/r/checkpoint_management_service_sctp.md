# checkpoint_management_service_sctp

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
module "checkpoint_management_service_sctp" {
  source = "./modules/checkpoint/r/checkpoint_management_service_sctp"

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
  # keep_connections_open_after_policy_installation - (optional) is a type of bool
  keep_connections_open_after_policy_installation = null
  # match_for_any - (optional) is a type of bool
  match_for_any = null
  # name - (required) is a type of string
  name = null
  # port - (optional) is a type of string
  port = null
  # session_timeout - (optional) is a type of number
  session_timeout = null
  # source_port - (optional) is a type of string
  source_port = null
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

variable "keep_connections_open_after_policy_installation" {
  description = "(optional) - Keep connections open after policy has been installed even if they are not allowed under the new policy. This overrides the settings in the Connection Persistence page. If you change this property, the change will not affect open connections, but only future connections."
  type        = bool
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

variable "port" {
  description = "(optional) - Port number. To specify a port range add a hyphen between the lowest and the highest port numbers, for example 44-45."
  type        = string
  default     = null
}

variable "session_timeout" {
  description = "(optional) - Time (in seconds) before the session times out."
  type        = number
  default     = null
}

variable "source_port" {
  description = "(optional) - Source port number. To specify a port range add a hyphen between the lowest and the highest port numbers, for example 44-45."
  type        = string
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
resource "checkpoint_management_service_sctp" "this" {
  aggressive_aging                                = var.aggressive_aging
  color                                           = var.color
  comments                                        = var.comments
  ignore_errors                                   = var.ignore_errors
  ignore_warnings                                 = var.ignore_warnings
  keep_connections_open_after_policy_installation = var.keep_connections_open_after_policy_installation
  match_for_any                                   = var.match_for_any
  name                                            = var.name
  port                                            = var.port
  session_timeout                                 = var.session_timeout
  source_port                                     = var.source_port
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
  value       = checkpoint_management_service_sctp.this.id
}

output "this" {
  value = checkpoint_management_service_sctp.this
}
```

[top](#index)