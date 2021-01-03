# checkpoint_management_checkpoint_host

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
module "checkpoint_management_checkpoint_host" {
  source = "./modules/checkpoint/r/checkpoint_management_checkpoint_host"

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
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # logs_settings - (optional) is a type of map of string
  logs_settings = {}
  # management_blades - (optional) is a type of map of string
  management_blades = {}
  # name - (required) is a type of string
  name = null
  # nat_settings - (optional) is a type of map of string
  nat_settings = {}
  # one_time_password - (optional) is a type of string
  one_time_password = null
  # os - (optional) is a type of string
  os = null
  # save_logs_locally - (optional) is a type of bool
  save_logs_locally = null
  # send_alerts_to_server - (optional) is a type of set of string
  send_alerts_to_server = []
  # send_logs_to_backup_server - (optional) is a type of set of string
  send_logs_to_backup_server = []
  # send_logs_to_server - (optional) is a type of set of string
  send_logs_to_server = []
  # tags - (optional) is a type of set of string
  tags = []
  # version - (optional) is a type of string
  version = null

  interfaces = [{
    color           = null
    comments        = null
    ignore_errors   = null
    ignore_warnings = null
    mask_length4    = null
    mask_length6    = null
    name            = null
    subnet4         = null
    subnet6         = null
    subnet_mask     = null
  }]
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
  description = "(optional) - Hardware name."
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

variable "ipv6_address" {
  description = "(optional) - IPv6 address."
  type        = string
  default     = null
}

variable "logs_settings" {
  description = "(optional) - Logs settings."
  type        = map(string)
  default     = null
}

variable "management_blades" {
  description = "(optional) - Management blades."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "nat_settings" {
  description = "(optional) - NAT settings."
  type        = map(string)
  default     = null
}

variable "one_time_password" {
  description = "(optional) - Secure internal connection one time password."
  type        = string
  default     = null
}

variable "os" {
  description = "(optional) - Operating system name."
  type        = string
  default     = null
}

variable "save_logs_locally" {
  description = "(optional) - Enable save logs locally."
  type        = bool
  default     = null
}

variable "send_alerts_to_server" {
  description = "(optional) - Collection of Server(s) to send alerts to identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "send_logs_to_backup_server" {
  description = "(optional) - Collection of Backup server(s) to send logs to identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "send_logs_to_server" {
  description = "(optional) - Collection of Server(s) to send logs to identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "version" {
  description = "(optional) - Checkpoint host platform version."
  type        = string
  default     = null
}

variable "interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      color           = string
      comments        = string
      ignore_errors   = bool
      ignore_warnings = bool
      mask_length4    = number
      mask_length6    = number
      name            = string
      subnet4         = string
      subnet6         = string
      subnet_mask     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_checkpoint_host" "this" {
  color                      = var.color
  comments                   = var.comments
  hardware                   = var.hardware
  ignore_errors              = var.ignore_errors
  ignore_warnings            = var.ignore_warnings
  ipv4_address               = var.ipv4_address
  ipv6_address               = var.ipv6_address
  logs_settings              = var.logs_settings
  management_blades          = var.management_blades
  name                       = var.name
  nat_settings               = var.nat_settings
  one_time_password          = var.one_time_password
  os                         = var.os
  save_logs_locally          = var.save_logs_locally
  send_alerts_to_server      = var.send_alerts_to_server
  send_logs_to_backup_server = var.send_logs_to_backup_server
  send_logs_to_server        = var.send_logs_to_server
  tags                       = var.tags
  version                    = var.version

  dynamic "interfaces" {
    for_each = var.interfaces
    content {
      color           = interfaces.value["color"]
      comments        = interfaces.value["comments"]
      ignore_errors   = interfaces.value["ignore_errors"]
      ignore_warnings = interfaces.value["ignore_warnings"]
      mask_length4    = interfaces.value["mask_length4"]
      mask_length6    = interfaces.value["mask_length6"]
      name            = interfaces.value["name"]
      subnet4         = interfaces.value["subnet4"]
      subnet6         = interfaces.value["subnet6"]
      subnet_mask     = interfaces.value["subnet_mask"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_checkpoint_host.this.id
}

output "sic_name" {
  description = "returns a string"
  value       = checkpoint_management_checkpoint_host.this.sic_name
}

output "sic_state" {
  description = "returns a string"
  value       = checkpoint_management_checkpoint_host.this.sic_state
}

output "this" {
  value = checkpoint_management_checkpoint_host.this
}
```

[top](#index)