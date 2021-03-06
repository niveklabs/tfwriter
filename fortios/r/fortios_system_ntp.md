# fortios_system_ntp

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_ntp" {
  source = "./modules/fortios/r/fortios_system_ntp"

  # authentication - (optional) is a type of string
  authentication = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # key - (optional) is a type of string
  key = null
  # key_id - (optional) is a type of number
  key_id = null
  # key_type - (optional) is a type of string
  key_type = null
  # ntpsync - (optional) is a type of string
  ntpsync = null
  # server_mode - (optional) is a type of string
  server_mode = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_ip6 - (optional) is a type of string
  source_ip6 = null
  # syncinterval - (optional) is a type of number
  syncinterval = null
  # type - (optional) is a type of string
  type = null

  interface = [{
    interface_name = null
  }]

  ntpserver = [{
    authentication          = null
    id                      = null
    interface               = null
    interface_select_method = null
    key                     = null
    key_id                  = null
    ntpv3                   = null
    server                  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "key_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntpsync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syncinterval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}

variable "ntpserver" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      authentication          = string
      id                      = number
      interface               = string
      interface_select_method = string
      key                     = string
      key_id                  = number
      ntpv3                   = string
      server                  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ntp" "this" {
  # authentication - (optional) is a type of string
  authentication = var.authentication
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # key - (optional) is a type of string
  key = var.key
  # key_id - (optional) is a type of number
  key_id = var.key_id
  # key_type - (optional) is a type of string
  key_type = var.key_type
  # ntpsync - (optional) is a type of string
  ntpsync = var.ntpsync
  # server_mode - (optional) is a type of string
  server_mode = var.server_mode
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # source_ip6 - (optional) is a type of string
  source_ip6 = var.source_ip6
  # syncinterval - (optional) is a type of number
  syncinterval = var.syncinterval
  # type - (optional) is a type of string
  type = var.type

  dynamic "interface" {
    for_each = var.interface
    content {
      # interface_name - (optional) is a type of string
      interface_name = interface.value["interface_name"]
    }
  }

  dynamic "ntpserver" {
    for_each = var.ntpserver
    content {
      # authentication - (optional) is a type of string
      authentication = ntpserver.value["authentication"]
      # id - (optional) is a type of number
      id = ntpserver.value["id"]
      # interface - (optional) is a type of string
      interface = ntpserver.value["interface"]
      # interface_select_method - (optional) is a type of string
      interface_select_method = ntpserver.value["interface_select_method"]
      # key - (optional) is a type of string
      key = ntpserver.value["key"]
      # key_id - (optional) is a type of number
      key_id = ntpserver.value["key_id"]
      # ntpv3 - (optional) is a type of string
      ntpv3 = ntpserver.value["ntpv3"]
      # server - (optional) is a type of string
      server = ntpserver.value["server"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "authentication" {
  description = "returns a string"
  value       = fortios_system_ntp.this.authentication
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ntp.this.id
}

output "key_id" {
  description = "returns a number"
  value       = fortios_system_ntp.this.key_id
}

output "key_type" {
  description = "returns a string"
  value       = fortios_system_ntp.this.key_type
}

output "ntpsync" {
  description = "returns a string"
  value       = fortios_system_ntp.this.ntpsync
}

output "server_mode" {
  description = "returns a string"
  value       = fortios_system_ntp.this.server_mode
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_ntp.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = fortios_system_ntp.this.source_ip6
}

output "syncinterval" {
  description = "returns a number"
  value       = fortios_system_ntp.this.syncinterval
}

output "type" {
  description = "returns a string"
  value       = fortios_system_ntp.this.type
}

output "this" {
  value = fortios_system_ntp.this
}
```

[top](#index)