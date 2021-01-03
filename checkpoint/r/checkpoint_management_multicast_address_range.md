# checkpoint_management_multicast_address_range

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
module "checkpoint_management_multicast_address_range" {
  source = "./modules/checkpoint/r/checkpoint_management_multicast_address_range"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # ipv4_address_first - (optional) is a type of string
  ipv4_address_first = null
  # ipv4_address_last - (optional) is a type of string
  ipv4_address_last = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # ipv6_address_first - (optional) is a type of string
  ipv6_address_first = null
  # ipv6_address_last - (optional) is a type of string
  ipv6_address_last = null
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

variable "ipv4_address" {
  description = "(optional) - IPv4 address."
  type        = string
  default     = null
}

variable "ipv4_address_first" {
  description = "(optional) - First IPv4 address in the range."
  type        = string
  default     = null
}

variable "ipv4_address_last" {
  description = "(optional) - Last IPv4 address in the range."
  type        = string
  default     = null
}

variable "ipv6_address" {
  description = "(optional) - IPv6 address."
  type        = string
  default     = null
}

variable "ipv6_address_first" {
  description = "(optional) - First IPv6 address in the range."
  type        = string
  default     = null
}

variable "ipv6_address_last" {
  description = "(optional) - Last IPv6 address in the range."
  type        = string
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
resource "checkpoint_management_multicast_address_range" "this" {
  color              = var.color
  comments           = var.comments
  ignore_errors      = var.ignore_errors
  ignore_warnings    = var.ignore_warnings
  ipv4_address       = var.ipv4_address
  ipv4_address_first = var.ipv4_address_first
  ipv4_address_last  = var.ipv4_address_last
  ipv6_address       = var.ipv6_address
  ipv6_address_first = var.ipv6_address_first
  ipv6_address_last  = var.ipv6_address_last
  name               = var.name
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_multicast_address_range.this.id
}

output "this" {
  value = checkpoint_management_multicast_address_range.this
}
```

[top](#index)