# panos_anti_spyware_security_profile

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
module "panos_anti_spyware_security_profile" {
  source = "./modules/panos/r/panos_anti_spyware_security_profile"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # packet_capture - (optional) is a type of string
  packet_capture = null
  # sinkhole_ipv4_address - (optional) is a type of string
  sinkhole_ipv4_address = null
  # sinkhole_ipv6_address - (optional) is a type of string
  sinkhole_ipv6_address = null
  # threat_exceptions - (optional) is a type of list of string
  threat_exceptions = []
  # vsys - (optional) is a type of string
  vsys = null

  botnet_list = [{
    action         = null
    name           = null
    packet_capture = null
  }]

  dns_category = [{
    action         = null
    log_level      = null
    name           = null
    packet_capture = null
  }]

  exception = [{
    action            = null
    block_ip_duration = null
    block_ip_track_by = null
    exempt_ips        = []
    name              = null
    packet_capture    = null
  }]

  rule = [{
    action            = null
    block_ip_duration = null
    block_ip_track_by = null
    category          = null
    name              = null
    packet_capture    = null
    severities        = []
    threat_name       = null
  }]

  white_list = [{
    description = null
    name        = null
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

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "packet_capture" {
  description = "(optional) - (PAN-OS 8.x only) Packet capture config"
  type        = string
  default     = null
}

variable "sinkhole_ipv4_address" {
  description = "(optional) - IPv4 sinkhole address"
  type        = string
  default     = null
}

variable "sinkhole_ipv6_address" {
  description = "(optional) - IPv6 sinkhole address"
  type        = string
  default     = null
}

variable "threat_exceptions" {
  description = "(optional) - List of threat exceptions"
  type        = list(string)
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "botnet_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action         = string
      name           = string
      packet_capture = string
    }
  ))
  default = []
}

variable "dns_category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action         = string
      log_level      = string
      name           = string
      packet_capture = string
    }
  ))
  default = []
}

variable "exception" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action            = string
      block_ip_duration = number
      block_ip_track_by = string
      exempt_ips        = list(string)
      name              = string
      packet_capture    = string
    }
  ))
  default = []
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action            = string
      block_ip_duration = number
      block_ip_track_by = string
      category          = string
      name              = string
      packet_capture    = string
      severities        = list(string)
      threat_name       = string
    }
  ))
  default = []
}

variable "white_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      name        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_anti_spyware_security_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # packet_capture - (optional) is a type of string
  packet_capture = var.packet_capture
  # sinkhole_ipv4_address - (optional) is a type of string
  sinkhole_ipv4_address = var.sinkhole_ipv4_address
  # sinkhole_ipv6_address - (optional) is a type of string
  sinkhole_ipv6_address = var.sinkhole_ipv6_address
  # threat_exceptions - (optional) is a type of list of string
  threat_exceptions = var.threat_exceptions
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "botnet_list" {
    for_each = var.botnet_list
    content {
      # action - (required) is a type of string
      action = botnet_list.value["action"]
      # name - (required) is a type of string
      name = botnet_list.value["name"]
      # packet_capture - (optional) is a type of string
      packet_capture = botnet_list.value["packet_capture"]
    }
  }

  dynamic "dns_category" {
    for_each = var.dns_category
    content {
      # action - (optional) is a type of string
      action = dns_category.value["action"]
      # log_level - (optional) is a type of string
      log_level = dns_category.value["log_level"]
      # name - (required) is a type of string
      name = dns_category.value["name"]
      # packet_capture - (optional) is a type of string
      packet_capture = dns_category.value["packet_capture"]
    }
  }

  dynamic "exception" {
    for_each = var.exception
    content {
      # action - (optional) is a type of string
      action = exception.value["action"]
      # block_ip_duration - (optional) is a type of number
      block_ip_duration = exception.value["block_ip_duration"]
      # block_ip_track_by - (optional) is a type of string
      block_ip_track_by = exception.value["block_ip_track_by"]
      # exempt_ips - (optional) is a type of list of string
      exempt_ips = exception.value["exempt_ips"]
      # name - (required) is a type of string
      name = exception.value["name"]
      # packet_capture - (optional) is a type of string
      packet_capture = exception.value["packet_capture"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {
      # action - (optional) is a type of string
      action = rule.value["action"]
      # block_ip_duration - (optional) is a type of number
      block_ip_duration = rule.value["block_ip_duration"]
      # block_ip_track_by - (optional) is a type of string
      block_ip_track_by = rule.value["block_ip_track_by"]
      # category - (required) is a type of string
      category = rule.value["category"]
      # name - (required) is a type of string
      name = rule.value["name"]
      # packet_capture - (optional) is a type of string
      packet_capture = rule.value["packet_capture"]
      # severities - (optional) is a type of list of string
      severities = rule.value["severities"]
      # threat_name - (optional) is a type of string
      threat_name = rule.value["threat_name"]
    }
  }

  dynamic "white_list" {
    for_each = var.white_list
    content {
      # description - (optional) is a type of string
      description = white_list.value["description"]
      # name - (required) is a type of string
      name = white_list.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_anti_spyware_security_profile.this.id
}

output "this" {
  value = panos_anti_spyware_security_profile.this
}
```

[top](#index)