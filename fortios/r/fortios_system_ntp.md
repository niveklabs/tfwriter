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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_ntp" {
  source = "./modules/fortios/r/fortios_system_ntp"

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
    authentication = null
    id             = null
    key            = null
    key_id         = null
    ntpv3          = null
    server         = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
      authentication = string
      id             = number
      key            = string
      key_id         = number
      ntpv3          = string
      server         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ntp" "this" {
  ntpsync      = var.ntpsync
  server_mode  = var.server_mode
  source_ip    = var.source_ip
  source_ip6   = var.source_ip6
  syncinterval = var.syncinterval
  type         = var.type

  dynamic "interface" {
    for_each = var.interface
    content {
      interface_name = interface.value["interface_name"]
    }
  }

  dynamic "ntpserver" {
    for_each = var.ntpserver
    content {
      authentication = ntpserver.value["authentication"]
      id             = ntpserver.value["id"]
      key            = ntpserver.value["key"]
      key_id         = ntpserver.value["key_id"]
      ntpv3          = ntpserver.value["ntpv3"]
      server         = ntpserver.value["server"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ntp.this.id
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