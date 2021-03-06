# fortios_log_threatweight

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
module "fortios_log_threatweight" {
  source = "./modules/fortios/r/fortios_log_threatweight"

  # blocked_connection - (optional) is a type of string
  blocked_connection = null
  # botnet_connection_detected - (optional) is a type of string
  botnet_connection_detected = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # failed_connection - (optional) is a type of string
  failed_connection = null
  # status - (optional) is a type of string
  status = null
  # url_block_detected - (optional) is a type of string
  url_block_detected = null

  application = [{
    category = null
    id       = null
    level    = null
  }]

  geolocation = [{
    country = null
    id      = null
    level   = null
  }]

  ips = [{
    critical_severity = null
    high_severity     = null
    info_severity     = null
    low_severity      = null
    medium_severity   = null
  }]

  level = [{
    critical = null
    high     = null
    low      = null
    medium   = null
  }]

  malware = [{
    botnet_connection          = null
    command_blocked            = null
    content_disarm             = null
    file_blocked               = null
    fsa_high_risk              = null
    fsa_malicious              = null
    fsa_medium_risk            = null
    malware_list               = null
    mimefragmented             = null
    oversized                  = null
    switch_proto               = null
    virus_file_type_executable = null
    virus_infected             = null
    virus_outbreak_prevention  = null
    virus_scan_error           = null
  }]

  web = [{
    category = null
    id       = null
    level    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "blocked_connection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "botnet_connection_detected" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "failed_connection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_block_detected" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = number
      id       = number
      level    = string
    }
  ))
  default = []
}

variable "geolocation" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      country = string
      id      = number
      level   = string
    }
  ))
  default = []
}

variable "ips" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      critical_severity = string
      high_severity     = string
      info_severity     = string
      low_severity      = string
      medium_severity   = string
    }
  ))
  default = []
}

variable "level" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      critical = number
      high     = number
      low      = number
      medium   = number
    }
  ))
  default = []
}

variable "malware" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      botnet_connection          = string
      command_blocked            = string
      content_disarm             = string
      file_blocked               = string
      fsa_high_risk              = string
      fsa_malicious              = string
      fsa_medium_risk            = string
      malware_list               = string
      mimefragmented             = string
      oversized                  = string
      switch_proto               = string
      virus_file_type_executable = string
      virus_infected             = string
      virus_outbreak_prevention  = string
      virus_scan_error           = string
    }
  ))
  default = []
}

variable "web" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = number
      id       = number
      level    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_threatweight" "this" {
  # blocked_connection - (optional) is a type of string
  blocked_connection = var.blocked_connection
  # botnet_connection_detected - (optional) is a type of string
  botnet_connection_detected = var.botnet_connection_detected
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # failed_connection - (optional) is a type of string
  failed_connection = var.failed_connection
  # status - (optional) is a type of string
  status = var.status
  # url_block_detected - (optional) is a type of string
  url_block_detected = var.url_block_detected

  dynamic "application" {
    for_each = var.application
    content {
      # category - (optional) is a type of number
      category = application.value["category"]
      # id - (optional) is a type of number
      id = application.value["id"]
      # level - (optional) is a type of string
      level = application.value["level"]
    }
  }

  dynamic "geolocation" {
    for_each = var.geolocation
    content {
      # country - (optional) is a type of string
      country = geolocation.value["country"]
      # id - (optional) is a type of number
      id = geolocation.value["id"]
      # level - (optional) is a type of string
      level = geolocation.value["level"]
    }
  }

  dynamic "ips" {
    for_each = var.ips
    content {
      # critical_severity - (optional) is a type of string
      critical_severity = ips.value["critical_severity"]
      # high_severity - (optional) is a type of string
      high_severity = ips.value["high_severity"]
      # info_severity - (optional) is a type of string
      info_severity = ips.value["info_severity"]
      # low_severity - (optional) is a type of string
      low_severity = ips.value["low_severity"]
      # medium_severity - (optional) is a type of string
      medium_severity = ips.value["medium_severity"]
    }
  }

  dynamic "level" {
    for_each = var.level
    content {
      # critical - (optional) is a type of number
      critical = level.value["critical"]
      # high - (optional) is a type of number
      high = level.value["high"]
      # low - (optional) is a type of number
      low = level.value["low"]
      # medium - (optional) is a type of number
      medium = level.value["medium"]
    }
  }

  dynamic "malware" {
    for_each = var.malware
    content {
      # botnet_connection - (optional) is a type of string
      botnet_connection = malware.value["botnet_connection"]
      # command_blocked - (optional) is a type of string
      command_blocked = malware.value["command_blocked"]
      # content_disarm - (optional) is a type of string
      content_disarm = malware.value["content_disarm"]
      # file_blocked - (optional) is a type of string
      file_blocked = malware.value["file_blocked"]
      # fsa_high_risk - (optional) is a type of string
      fsa_high_risk = malware.value["fsa_high_risk"]
      # fsa_malicious - (optional) is a type of string
      fsa_malicious = malware.value["fsa_malicious"]
      # fsa_medium_risk - (optional) is a type of string
      fsa_medium_risk = malware.value["fsa_medium_risk"]
      # malware_list - (optional) is a type of string
      malware_list = malware.value["malware_list"]
      # mimefragmented - (optional) is a type of string
      mimefragmented = malware.value["mimefragmented"]
      # oversized - (optional) is a type of string
      oversized = malware.value["oversized"]
      # switch_proto - (optional) is a type of string
      switch_proto = malware.value["switch_proto"]
      # virus_file_type_executable - (optional) is a type of string
      virus_file_type_executable = malware.value["virus_file_type_executable"]
      # virus_infected - (optional) is a type of string
      virus_infected = malware.value["virus_infected"]
      # virus_outbreak_prevention - (optional) is a type of string
      virus_outbreak_prevention = malware.value["virus_outbreak_prevention"]
      # virus_scan_error - (optional) is a type of string
      virus_scan_error = malware.value["virus_scan_error"]
    }
  }

  dynamic "web" {
    for_each = var.web
    content {
      # category - (optional) is a type of number
      category = web.value["category"]
      # id - (optional) is a type of number
      id = web.value["id"]
      # level - (optional) is a type of string
      level = web.value["level"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "blocked_connection" {
  description = "returns a string"
  value       = fortios_log_threatweight.this.blocked_connection
}

output "botnet_connection_detected" {
  description = "returns a string"
  value       = fortios_log_threatweight.this.botnet_connection_detected
}

output "failed_connection" {
  description = "returns a string"
  value       = fortios_log_threatweight.this.failed_connection
}

output "id" {
  description = "returns a string"
  value       = fortios_log_threatweight.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_log_threatweight.this.status
}

output "url_block_detected" {
  description = "returns a string"
  value       = fortios_log_threatweight.this.url_block_detected
}

output "this" {
  value = fortios_log_threatweight.this
}
```

[top](#index)