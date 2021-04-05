# panos_dos_protection_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_dos_protection_profile" {
  source = "./modules/panos/r/panos_dos_protection_profile"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # enable_sessions_protections - (optional) is a type of bool
  enable_sessions_protections = null
  # max_concurrent_sessions - (optional) is a type of number
  max_concurrent_sessions = null
  # name - (required) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
  # vsys - (optional) is a type of string
  vsys = null

  icmp = [{
    activate_rate  = null
    alarm_rate     = null
    block_duration = null
    enable         = null
    max_rate       = null
  }]

  icmpv6 = [{
    activate_rate  = null
    alarm_rate     = null
    block_duration = null
    enable         = null
    max_rate       = null
  }]

  other = [{
    activate_rate  = null
    alarm_rate     = null
    block_duration = null
    enable         = null
    max_rate       = null
  }]

  syn = [{
    action         = null
    activate_rate  = null
    alarm_rate     = null
    block_duration = null
    enable         = null
    max_rate       = null
  }]

  udp = [{
    activate_rate  = null
    alarm_rate     = null
    block_duration = null
    enable         = null
    max_rate       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_sessions_protections" {
  description = "(optional) - Enable sessions protections"
  type        = bool
  default     = null
}

variable "max_concurrent_sessions" {
  description = "(optional) - Max concurrent sessions"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "type" {
  description = "(optional) - The profile type"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      activate_rate  = number
      alarm_rate     = number
      block_duration = number
      enable         = bool
      max_rate       = number
    }
  ))
  default = []
}

variable "icmpv6" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      activate_rate  = number
      alarm_rate     = number
      block_duration = number
      enable         = bool
      max_rate       = number
    }
  ))
  default = []
}

variable "other" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      activate_rate  = number
      alarm_rate     = number
      block_duration = number
      enable         = bool
      max_rate       = number
    }
  ))
  default = []
}

variable "syn" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action         = string
      activate_rate  = number
      alarm_rate     = number
      block_duration = number
      enable         = bool
      max_rate       = number
    }
  ))
  default = []
}

variable "udp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      activate_rate  = number
      alarm_rate     = number
      block_duration = number
      enable         = bool
      max_rate       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_dos_protection_profile" "this" {
  description                 = var.description
  device_group                = var.device_group
  enable_sessions_protections = var.enable_sessions_protections
  max_concurrent_sessions     = var.max_concurrent_sessions
  name                        = var.name
  type                        = var.type
  vsys                        = var.vsys

  dynamic "icmp" {
    for_each = var.icmp
    content {
      activate_rate  = icmp.value["activate_rate"]
      alarm_rate     = icmp.value["alarm_rate"]
      block_duration = icmp.value["block_duration"]
      enable         = icmp.value["enable"]
      max_rate       = icmp.value["max_rate"]
    }
  }

  dynamic "icmpv6" {
    for_each = var.icmpv6
    content {
      activate_rate  = icmpv6.value["activate_rate"]
      alarm_rate     = icmpv6.value["alarm_rate"]
      block_duration = icmpv6.value["block_duration"]
      enable         = icmpv6.value["enable"]
      max_rate       = icmpv6.value["max_rate"]
    }
  }

  dynamic "other" {
    for_each = var.other
    content {
      activate_rate  = other.value["activate_rate"]
      alarm_rate     = other.value["alarm_rate"]
      block_duration = other.value["block_duration"]
      enable         = other.value["enable"]
      max_rate       = other.value["max_rate"]
    }
  }

  dynamic "syn" {
    for_each = var.syn
    content {
      action         = syn.value["action"]
      activate_rate  = syn.value["activate_rate"]
      alarm_rate     = syn.value["alarm_rate"]
      block_duration = syn.value["block_duration"]
      enable         = syn.value["enable"]
      max_rate       = syn.value["max_rate"]
    }
  }

  dynamic "udp" {
    for_each = var.udp
    content {
      activate_rate  = udp.value["activate_rate"]
      alarm_rate     = udp.value["alarm_rate"]
      block_duration = udp.value["block_duration"]
      enable         = udp.value["enable"]
      max_rate       = udp.value["max_rate"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_dos_protection_profile.this.id
}

output "this" {
  value = panos_dos_protection_profile.this
}
```

[top](#index)