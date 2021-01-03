# checkpoint_management_mds

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
module "checkpoint_management_mds" {
  source = "./modules/checkpoint/r/checkpoint_management_mds"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # hardware - (optional) is a type of string
  hardware = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ip_pool_first - (optional) is a type of string
  ip_pool_first = null
  # ip_pool_last - (optional) is a type of string
  ip_pool_last = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # name - (required) is a type of string
  name = null
  # one_time_password - (optional) is a type of string
  one_time_password = null
  # os - (optional) is a type of string
  os = null
  # server_type - (optional) is a type of string
  server_type = null
  # tags - (optional) is a type of set of string
  tags = []
  # version - (optional) is a type of string
  version = null
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

variable "hardware" {
  description = "(optional) - Hardware name. For example: Open server, Smart-1, Other."
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

variable "ip_pool_first" {
  description = "(optional) - First IP address in the range."
  type        = string
  default     = null
}

variable "ip_pool_last" {
  description = "(optional) - Last IP address in the range."
  type        = string
  default     = null
}

variable "ipv4_address" {
  description = "(optional) - IPv4 address."
  type        = string
  default     = null
}

variable "ipv6_address" {
  description = "(optional) - IPv6 address."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "one_time_password" {
  description = "(optional) - Secure internal connection one time password."
  type        = string
  default     = null
}

variable "os" {
  description = "(optional) - Operating system name. For example: Gaia, Linux, SecurePlatform."
  type        = string
  default     = null
}

variable "server_type" {
  description = "(optional) - Type of the management server."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "version" {
  description = "(optional) - System version."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_mds" "this" {
  color             = var.color
  comments          = var.comments
  hardware          = var.hardware
  ignore_errors     = var.ignore_errors
  ignore_warnings   = var.ignore_warnings
  ip_pool_first     = var.ip_pool_first
  ip_pool_last      = var.ip_pool_last
  ipv4_address      = var.ipv4_address
  ipv6_address      = var.ipv6_address
  name              = var.name
  one_time_password = var.one_time_password
  os                = var.os
  server_type       = var.server_type
  tags              = var.tags
  version           = var.version
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a set of string"
  value       = checkpoint_management_mds.this.domains
}

output "global_domains" {
  description = "returns a set of string"
  value       = checkpoint_management_mds.this.global_domains
}

output "id" {
  description = "returns a string"
  value       = checkpoint_management_mds.this.id
}

output "sic_name" {
  description = "returns a string"
  value       = checkpoint_management_mds.this.sic_name
}

output "sic_state" {
  description = "returns a string"
  value       = checkpoint_management_mds.this.sic_state
}

output "this" {
  value = checkpoint_management_mds.this
}
```

[top](#index)