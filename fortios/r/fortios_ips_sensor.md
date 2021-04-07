# fortios_ips_sensor

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
module "fortios_ips_sensor" {
  source = "./modules/fortios/r/fortios_ips_sensor"

  # block_malicious_url - (optional) is a type of string
  block_malicious_url = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # extended_log - (optional) is a type of string
  extended_log = null
  # name - (required) is a type of string
  name = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = null

  entries = [{
    action      = null
    application = null
    cve = [{
      cve_entry = null
    }]
    exempt_ip = [{
      dst_ip = null
      id     = null
      src_ip = null
    }]
    id                 = null
    location           = null
    log                = null
    log_attack_context = null
    log_packet         = null
    os                 = null
    protocol           = null
    quarantine         = null
    quarantine_expiry  = null
    quarantine_log     = null
    rate_count         = null
    rate_duration      = null
    rate_mode          = null
    rate_track         = null
    rule = [{
      id = null
    }]
    severity = null
    status   = null
  }]

  filter = [{
    action            = null
    application       = null
    location          = null
    log               = null
    log_packet        = null
    name              = null
    os                = null
    protocol          = null
    quarantine        = null
    quarantine_expiry = null
    quarantine_log    = null
    severity          = null
    status            = null
  }]

  override = [{
    action = null
    exempt_ip = [{
      dst_ip = null
      id     = null
      src_ip = null
    }]
    log               = null
    log_packet        = null
    quarantine        = null
    quarantine_expiry = null
    quarantine_log    = null
    rule_id           = null
    status            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block_malicious_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_botnet_connections" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      application = string
      cve = list(object(
        {
          cve_entry = string
        }
      ))
      exempt_ip = list(object(
        {
          dst_ip = string
          id     = number
          src_ip = string
        }
      ))
      id                 = number
      location           = string
      log                = string
      log_attack_context = string
      log_packet         = string
      os                 = string
      protocol           = string
      quarantine         = string
      quarantine_expiry  = string
      quarantine_log     = string
      rate_count         = number
      rate_duration      = number
      rate_mode          = string
      rate_track         = string
      rule = list(object(
        {
          id = number
        }
      ))
      severity = string
      status   = string
    }
  ))
  default = []
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action            = string
      application       = string
      location          = string
      log               = string
      log_packet        = string
      name              = string
      os                = string
      protocol          = string
      quarantine        = string
      quarantine_expiry = number
      quarantine_log    = string
      severity          = string
      status            = string
    }
  ))
  default = []
}

variable "override" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      exempt_ip = list(object(
        {
          dst_ip = string
          id     = number
          src_ip = string
        }
      ))
      log               = string
      log_packet        = string
      quarantine        = string
      quarantine_expiry = number
      quarantine_log    = string
      rule_id           = number
      status            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_sensor" "this" {
  # block_malicious_url - (optional) is a type of string
  block_malicious_url = var.block_malicious_url
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # extended_log - (optional) is a type of string
  extended_log = var.extended_log
  # name - (required) is a type of string
  name = var.name
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = var.replacemsg_group
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = var.scan_botnet_connections

  dynamic "entries" {
    for_each = var.entries
    content {
      # action - (optional) is a type of string
      action = entries.value["action"]
      # application - (optional) is a type of string
      application = entries.value["application"]
      # id - (optional) is a type of number
      id = entries.value["id"]
      # location - (optional) is a type of string
      location = entries.value["location"]
      # log - (optional) is a type of string
      log = entries.value["log"]
      # log_attack_context - (optional) is a type of string
      log_attack_context = entries.value["log_attack_context"]
      # log_packet - (optional) is a type of string
      log_packet = entries.value["log_packet"]
      # os - (optional) is a type of string
      os = entries.value["os"]
      # protocol - (optional) is a type of string
      protocol = entries.value["protocol"]
      # quarantine - (optional) is a type of string
      quarantine = entries.value["quarantine"]
      # quarantine_expiry - (optional) is a type of string
      quarantine_expiry = entries.value["quarantine_expiry"]
      # quarantine_log - (optional) is a type of string
      quarantine_log = entries.value["quarantine_log"]
      # rate_count - (optional) is a type of number
      rate_count = entries.value["rate_count"]
      # rate_duration - (optional) is a type of number
      rate_duration = entries.value["rate_duration"]
      # rate_mode - (optional) is a type of string
      rate_mode = entries.value["rate_mode"]
      # rate_track - (optional) is a type of string
      rate_track = entries.value["rate_track"]
      # severity - (optional) is a type of string
      severity = entries.value["severity"]
      # status - (optional) is a type of string
      status = entries.value["status"]

      dynamic "cve" {
        for_each = entries.value.cve
        content {
          # cve_entry - (optional) is a type of string
          cve_entry = cve.value["cve_entry"]
        }
      }

      dynamic "exempt_ip" {
        for_each = entries.value.exempt_ip
        content {
          # dst_ip - (optional) is a type of string
          dst_ip = exempt_ip.value["dst_ip"]
          # id - (optional) is a type of number
          id = exempt_ip.value["id"]
          # src_ip - (optional) is a type of string
          src_ip = exempt_ip.value["src_ip"]
        }
      }

      dynamic "rule" {
        for_each = entries.value.rule
        content {
          # id - (optional) is a type of number
          id = rule.value["id"]
        }
      }

    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      # action - (optional) is a type of string
      action = filter.value["action"]
      # application - (optional) is a type of string
      application = filter.value["application"]
      # location - (optional) is a type of string
      location = filter.value["location"]
      # log - (optional) is a type of string
      log = filter.value["log"]
      # log_packet - (optional) is a type of string
      log_packet = filter.value["log_packet"]
      # name - (optional) is a type of string
      name = filter.value["name"]
      # os - (optional) is a type of string
      os = filter.value["os"]
      # protocol - (optional) is a type of string
      protocol = filter.value["protocol"]
      # quarantine - (optional) is a type of string
      quarantine = filter.value["quarantine"]
      # quarantine_expiry - (optional) is a type of number
      quarantine_expiry = filter.value["quarantine_expiry"]
      # quarantine_log - (optional) is a type of string
      quarantine_log = filter.value["quarantine_log"]
      # severity - (optional) is a type of string
      severity = filter.value["severity"]
      # status - (optional) is a type of string
      status = filter.value["status"]
    }
  }

  dynamic "override" {
    for_each = var.override
    content {
      # action - (optional) is a type of string
      action = override.value["action"]
      # log - (optional) is a type of string
      log = override.value["log"]
      # log_packet - (optional) is a type of string
      log_packet = override.value["log_packet"]
      # quarantine - (optional) is a type of string
      quarantine = override.value["quarantine"]
      # quarantine_expiry - (optional) is a type of number
      quarantine_expiry = override.value["quarantine_expiry"]
      # quarantine_log - (optional) is a type of string
      quarantine_log = override.value["quarantine_log"]
      # rule_id - (optional) is a type of number
      rule_id = override.value["rule_id"]
      # status - (optional) is a type of string
      status = override.value["status"]

      dynamic "exempt_ip" {
        for_each = override.value.exempt_ip
        content {
          # dst_ip - (optional) is a type of string
          dst_ip = exempt_ip.value["dst_ip"]
          # id - (optional) is a type of number
          id = exempt_ip.value["id"]
          # src_ip - (optional) is a type of string
          src_ip = exempt_ip.value["src_ip"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "block_malicious_url" {
  description = "returns a string"
  value       = fortios_ips_sensor.this.block_malicious_url
}

output "extended_log" {
  description = "returns a string"
  value       = fortios_ips_sensor.this.extended_log
}

output "id" {
  description = "returns a string"
  value       = fortios_ips_sensor.this.id
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_ips_sensor.this.replacemsg_group
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = fortios_ips_sensor.this.scan_botnet_connections
}

output "this" {
  value = fortios_ips_sensor.this
}
```

[top](#index)