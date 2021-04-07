# panos_panorama_application_object

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
module "panos_panorama_application_object" {
  source = "./modules/panos/r/panos_panorama_application_object"

  # able_to_file_transfer - (optional) is a type of bool
  able_to_file_transfer = null
  # alg_disable_capability - (optional) is a type of string
  alg_disable_capability = null
  # category - (required) is a type of string
  category = null
  # continue_scanning_for_other_applications - (optional) is a type of bool
  continue_scanning_for_other_applications = null
  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # evasive_behavior - (optional) is a type of bool
  evasive_behavior = null
  # excessive_bandwidth - (optional) is a type of bool
  excessive_bandwidth = null
  # has_known_vulnerability - (optional) is a type of bool
  has_known_vulnerability = null
  # name - (required) is a type of string
  name = null
  # no_app_id_caching - (optional) is a type of bool
  no_app_id_caching = null
  # parent_app - (optional) is a type of string
  parent_app = null
  # pervasive_use - (optional) is a type of bool
  pervasive_use = null
  # prone_to_misuse - (optional) is a type of bool
  prone_to_misuse = null
  # risk - (optional) is a type of number
  risk = null
  # subcategory - (required) is a type of string
  subcategory = null
  # technology - (required) is a type of string
  technology = null
  # tunnels_other_applications - (optional) is a type of bool
  tunnels_other_applications = null
  # used_by_malware - (optional) is a type of bool
  used_by_malware = null

  defaults = [{
    icmp = [{
      code = null
      type = null
    }]
    icmp6 = [{
      code = null
      type = null
    }]
    ip_protocol = [{
      value = null
    }]
    port = [{
      ports = []
    }]
  }]

  scanning = [{
    data_patterns = null
    file_types    = null
    viruses       = null
  }]

  timeout_settings = [{
    tcp_half_closed = null
    tcp_time_wait   = null
    tcp_timeout     = null
    timeout         = null
    udp_timeout     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "able_to_file_transfer" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "alg_disable_capability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(required)"
  type        = string
}

variable "continue_scanning_for_other_applications" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "evasive_behavior" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "excessive_bandwidth" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "has_known_vulnerability" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "no_app_id_caching" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "parent_app" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pervasive_use" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "prone_to_misuse" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "risk" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "subcategory" {
  description = "(required)"
  type        = string
}

variable "technology" {
  description = "(required)"
  type        = string
}

variable "tunnels_other_applications" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "used_by_malware" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "defaults" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      icmp = list(object(
        {
          code = number
          type = number
        }
      ))
      icmp6 = list(object(
        {
          code = number
          type = number
        }
      ))
      ip_protocol = list(object(
        {
          value = number
        }
      ))
      port = list(object(
        {
          ports = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "scanning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_patterns = bool
      file_types    = bool
      viruses       = bool
    }
  ))
  default = []
}

variable "timeout_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      tcp_half_closed = number
      tcp_time_wait   = number
      tcp_timeout     = number
      timeout         = number
      udp_timeout     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_application_object" "this" {
  # able_to_file_transfer - (optional) is a type of bool
  able_to_file_transfer = var.able_to_file_transfer
  # alg_disable_capability - (optional) is a type of string
  alg_disable_capability = var.alg_disable_capability
  # category - (required) is a type of string
  category = var.category
  # continue_scanning_for_other_applications - (optional) is a type of bool
  continue_scanning_for_other_applications = var.continue_scanning_for_other_applications
  # description - (optional) is a type of string
  description = var.description
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # evasive_behavior - (optional) is a type of bool
  evasive_behavior = var.evasive_behavior
  # excessive_bandwidth - (optional) is a type of bool
  excessive_bandwidth = var.excessive_bandwidth
  # has_known_vulnerability - (optional) is a type of bool
  has_known_vulnerability = var.has_known_vulnerability
  # name - (required) is a type of string
  name = var.name
  # no_app_id_caching - (optional) is a type of bool
  no_app_id_caching = var.no_app_id_caching
  # parent_app - (optional) is a type of string
  parent_app = var.parent_app
  # pervasive_use - (optional) is a type of bool
  pervasive_use = var.pervasive_use
  # prone_to_misuse - (optional) is a type of bool
  prone_to_misuse = var.prone_to_misuse
  # risk - (optional) is a type of number
  risk = var.risk
  # subcategory - (required) is a type of string
  subcategory = var.subcategory
  # technology - (required) is a type of string
  technology = var.technology
  # tunnels_other_applications - (optional) is a type of bool
  tunnels_other_applications = var.tunnels_other_applications
  # used_by_malware - (optional) is a type of bool
  used_by_malware = var.used_by_malware

  dynamic "defaults" {
    for_each = var.defaults
    content {

      dynamic "icmp" {
        for_each = defaults.value.icmp
        content {
          # code - (optional) is a type of number
          code = icmp.value["code"]
          # type - (required) is a type of number
          type = icmp.value["type"]
        }
      }

      dynamic "icmp6" {
        for_each = defaults.value.icmp6
        content {
          # code - (optional) is a type of number
          code = icmp6.value["code"]
          # type - (required) is a type of number
          type = icmp6.value["type"]
        }
      }

      dynamic "ip_protocol" {
        for_each = defaults.value.ip_protocol
        content {
          # value - (required) is a type of number
          value = ip_protocol.value["value"]
        }
      }

      dynamic "port" {
        for_each = defaults.value.port
        content {
          # ports - (required) is a type of list of string
          ports = port.value["ports"]
        }
      }

    }
  }

  dynamic "scanning" {
    for_each = var.scanning
    content {
      # data_patterns - (optional) is a type of bool
      data_patterns = scanning.value["data_patterns"]
      # file_types - (optional) is a type of bool
      file_types = scanning.value["file_types"]
      # viruses - (optional) is a type of bool
      viruses = scanning.value["viruses"]
    }
  }

  dynamic "timeout_settings" {
    for_each = var.timeout_settings
    content {
      # tcp_half_closed - (optional) is a type of number
      tcp_half_closed = timeout_settings.value["tcp_half_closed"]
      # tcp_time_wait - (optional) is a type of number
      tcp_time_wait = timeout_settings.value["tcp_time_wait"]
      # tcp_timeout - (optional) is a type of number
      tcp_timeout = timeout_settings.value["tcp_timeout"]
      # timeout - (optional) is a type of number
      timeout = timeout_settings.value["timeout"]
      # udp_timeout - (optional) is a type of number
      udp_timeout = timeout_settings.value["udp_timeout"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_application_object.this.id
}

output "this" {
  value = panos_panorama_application_object.this
}
```

[top](#index)