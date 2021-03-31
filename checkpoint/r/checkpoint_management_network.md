# checkpoint_management_network

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
module "checkpoint_management_network" {
  source = "./modules/checkpoint/r/checkpoint_management_network"

  # broadcast - (optional) is a type of string
  broadcast = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # mask_length4 - (optional) is a type of number
  mask_length4 = null
  # mask_length6 - (optional) is a type of number
  mask_length6 = null
  # name - (required) is a type of string
  name = null
  # nat_settings - (optional) is a type of map of string
  nat_settings = {}
  # subnet4 - (optional) is a type of string
  subnet4 = null
  # subnet6 - (optional) is a type of string
  subnet6 = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "broadcast" {
  description = "(optional) - Allow broadcast address inclusion."
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

variable "mask_length4" {
  description = "(optional) - IPv4 network mask length."
  type        = number
  default     = null
}

variable "mask_length6" {
  description = "(optional) - IPv6 network mask length."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Object name. Should be unique in the domain."
  type        = string
}

variable "nat_settings" {
  description = "(optional) - NAT settings."
  type        = map(string)
  default     = null
}

variable "subnet4" {
  description = "(optional) - IPv4 network address."
  type        = string
  default     = null
}

variable "subnet6" {
  description = "(optional) - IPv6 network address."
  type        = string
  default     = null
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
resource "checkpoint_management_network" "this" {
  broadcast       = var.broadcast
  color           = var.color
  comments        = var.comments
  ignore_errors   = var.ignore_errors
  ignore_warnings = var.ignore_warnings
  mask_length4    = var.mask_length4
  mask_length6    = var.mask_length6
  name            = var.name
  nat_settings    = var.nat_settings
  subnet4         = var.subnet4
  subnet6         = var.subnet6
  tags            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_network.this.id
}

output "this" {
  value = checkpoint_management_network.this
}
```

[top](#index)