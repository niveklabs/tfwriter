# checkpoint_management_wildcard

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
module "checkpoint_management_wildcard" {
  source = "./modules/checkpoint/r/checkpoint_management_wildcard"

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
  # ipv4_mask_wildcard - (optional) is a type of string
  ipv4_mask_wildcard = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # ipv6_mask_wildcard - (optional) is a type of string
  ipv6_mask_wildcard = null
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

variable "ipv4_mask_wildcard" {
  description = "(optional) - IPv4 mask wildcard."
  type        = string
  default     = null
}

variable "ipv6_address" {
  description = "(optional) - IPv6 address."
  type        = string
  default     = null
}

variable "ipv6_mask_wildcard" {
  description = "(optional) - IPv6 mask wildcard."
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
resource "checkpoint_management_wildcard" "this" {
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # ipv4_address - (optional) is a type of string
  ipv4_address = var.ipv4_address
  # ipv4_mask_wildcard - (optional) is a type of string
  ipv4_mask_wildcard = var.ipv4_mask_wildcard
  # ipv6_address - (optional) is a type of string
  ipv6_address = var.ipv6_address
  # ipv6_mask_wildcard - (optional) is a type of string
  ipv6_mask_wildcard = var.ipv6_mask_wildcard
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_wildcard.this.id
}

output "this" {
  value = checkpoint_management_wildcard.this
}
```

[top](#index)