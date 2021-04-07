# panos_url_filtering_security_profile

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
module "panos_url_filtering_security_profile" {
  source = "./modules/panos/r/panos_url_filtering_security_profile"

  # alert_categories - (optional) is a type of list of string
  alert_categories = []
  # allow_categories - (optional) is a type of list of string
  allow_categories = []
  # allow_list - (optional) is a type of list of string
  allow_list = []
  # block_categories - (optional) is a type of list of string
  block_categories = []
  # block_list - (optional) is a type of list of string
  block_list = []
  # block_list_action - (optional) is a type of string
  block_list_action = null
  # continue_categories - (optional) is a type of list of string
  continue_categories = []
  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # dynamic_url - (optional) is a type of bool
  dynamic_url = null
  # expired_license_action - (optional) is a type of bool
  expired_license_action = null
  # log_container_page_only - (optional) is a type of bool
  log_container_page_only = null
  # log_http_header_referer - (optional) is a type of bool
  log_http_header_referer = null
  # log_http_header_user_agent - (optional) is a type of bool
  log_http_header_user_agent = null
  # log_http_header_xff - (optional) is a type of bool
  log_http_header_xff = null
  # machine_learning_exceptions - (optional) is a type of list of string
  machine_learning_exceptions = []
  # name - (required) is a type of string
  name = null
  # override_categories - (optional) is a type of list of string
  override_categories = []
  # safe_search_enforcement - (optional) is a type of bool
  safe_search_enforcement = null
  # track_container_page - (optional) is a type of bool
  track_container_page = null
  # ucd_alert_categories - (optional) is a type of list of string
  ucd_alert_categories = []
  # ucd_allow_categories - (optional) is a type of list of string
  ucd_allow_categories = []
  # ucd_block_categories - (optional) is a type of list of string
  ucd_block_categories = []
  # ucd_continue_categories - (optional) is a type of list of string
  ucd_continue_categories = []
  # ucd_log_severity - (optional) is a type of string
  ucd_log_severity = null
  # ucd_mode - (optional) is a type of string
  ucd_mode = null
  # ucd_mode_group_mapping - (optional) is a type of string
  ucd_mode_group_mapping = null
  # vsys - (optional) is a type of string
  vsys = null

  http_header_insertion = [{
    domains = []
    http_header = [{
      header = null
      log    = null
      name   = null
      value  = null
    }]
    name = null
    type = null
  }]

  machine_learning_model = [{
    action = null
    model  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alert_categories" {
  description = "(optional) - List of categories to alert"
  type        = list(string)
  default     = null
}

variable "allow_categories" {
  description = "(optional) - List of categories to allow"
  type        = list(string)
  default     = null
}

variable "allow_list" {
  description = "(optional) - (Removed in PAN-OS 9.0) Allow list"
  type        = list(string)
  default     = null
}

variable "block_categories" {
  description = "(optional) - List of categories to block"
  type        = list(string)
  default     = null
}

variable "block_list" {
  description = "(optional) - (Removed in PAN-OS 9.0) Block list"
  type        = list(string)
  default     = null
}

variable "block_list_action" {
  description = "(optional) - (Removed in PAN-OS 9.0) Block list action"
  type        = string
  default     = null
}

variable "continue_categories" {
  description = "(optional) - List of categories to continue"
  type        = list(string)
  default     = null
}

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

variable "dynamic_url" {
  description = "(optional) - (Removed in PAN-OS 9.0) Dynamic URL"
  type        = bool
  default     = null
}

variable "expired_license_action" {
  description = "(optional) - (Removed in PAN-OS 9.0) Expired license action"
  type        = bool
  default     = null
}

variable "log_container_page_only" {
  description = "(optional) - Set to true to log container page only"
  type        = bool
  default     = null
}

variable "log_http_header_referer" {
  description = "(optional) - HTTP Header Logging: Referer"
  type        = bool
  default     = null
}

variable "log_http_header_user_agent" {
  description = "(optional) - HTTP Header Logging: User-Agent"
  type        = bool
  default     = null
}

variable "log_http_header_xff" {
  description = "(optional) - HTTP Header Logging: X-Forwarded-For"
  type        = bool
  default     = null
}

variable "machine_learning_exceptions" {
  description = "(optional) - (PAN-OS 10.0+) List of machine learning exceptions"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "override_categories" {
  description = "(optional) - List of categories to allow"
  type        = list(string)
  default     = null
}

variable "safe_search_enforcement" {
  description = "(optional) - Set to true for safe search enforcement"
  type        = bool
  default     = null
}

variable "track_container_page" {
  description = "(optional) - Set to true to track the container page"
  type        = bool
  default     = null
}

variable "ucd_alert_categories" {
  description = "(optional) - (PAN-OS 8.0+) Categories alerted on with user credential submission"
  type        = list(string)
  default     = null
}

variable "ucd_allow_categories" {
  description = "(optional) - (PAN-OS 8.0+) Categories allowed with user credential submission"
  type        = list(string)
  default     = null
}

variable "ucd_block_categories" {
  description = "(optional) - (PAN-OS 8.0+) Categories blocked with user credential submission"
  type        = list(string)
  default     = null
}

variable "ucd_continue_categories" {
  description = "(optional) - (PAN-OS 8.0+) Categories continued with user credential submission"
  type        = list(string)
  default     = null
}

variable "ucd_log_severity" {
  description = "(optional) - (PAN-OS 8.0+) User credential detection: valid username detected log severity"
  type        = string
  default     = null
}

variable "ucd_mode" {
  description = "(optional) - (PAN-OS 8.0+) User credential detection mode"
  type        = string
  default     = null
}

variable "ucd_mode_group_mapping" {
  description = "(optional) - (PAN-OS 8.0+, ucd_mode = group-mapping) User credential detection: the group mapping settings"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_header_insertion" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      domains = list(string)
      http_header = list(object(
        {
          header = string
          log    = bool
          name   = string
          value  = string
        }
      ))
      name = string
      type = string
    }
  ))
  default = []
}

variable "machine_learning_model" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      model  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_url_filtering_security_profile" "this" {
  # alert_categories - (optional) is a type of list of string
  alert_categories = var.alert_categories
  # allow_categories - (optional) is a type of list of string
  allow_categories = var.allow_categories
  # allow_list - (optional) is a type of list of string
  allow_list = var.allow_list
  # block_categories - (optional) is a type of list of string
  block_categories = var.block_categories
  # block_list - (optional) is a type of list of string
  block_list = var.block_list
  # block_list_action - (optional) is a type of string
  block_list_action = var.block_list_action
  # continue_categories - (optional) is a type of list of string
  continue_categories = var.continue_categories
  # description - (optional) is a type of string
  description = var.description
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # dynamic_url - (optional) is a type of bool
  dynamic_url = var.dynamic_url
  # expired_license_action - (optional) is a type of bool
  expired_license_action = var.expired_license_action
  # log_container_page_only - (optional) is a type of bool
  log_container_page_only = var.log_container_page_only
  # log_http_header_referer - (optional) is a type of bool
  log_http_header_referer = var.log_http_header_referer
  # log_http_header_user_agent - (optional) is a type of bool
  log_http_header_user_agent = var.log_http_header_user_agent
  # log_http_header_xff - (optional) is a type of bool
  log_http_header_xff = var.log_http_header_xff
  # machine_learning_exceptions - (optional) is a type of list of string
  machine_learning_exceptions = var.machine_learning_exceptions
  # name - (required) is a type of string
  name = var.name
  # override_categories - (optional) is a type of list of string
  override_categories = var.override_categories
  # safe_search_enforcement - (optional) is a type of bool
  safe_search_enforcement = var.safe_search_enforcement
  # track_container_page - (optional) is a type of bool
  track_container_page = var.track_container_page
  # ucd_alert_categories - (optional) is a type of list of string
  ucd_alert_categories = var.ucd_alert_categories
  # ucd_allow_categories - (optional) is a type of list of string
  ucd_allow_categories = var.ucd_allow_categories
  # ucd_block_categories - (optional) is a type of list of string
  ucd_block_categories = var.ucd_block_categories
  # ucd_continue_categories - (optional) is a type of list of string
  ucd_continue_categories = var.ucd_continue_categories
  # ucd_log_severity - (optional) is a type of string
  ucd_log_severity = var.ucd_log_severity
  # ucd_mode - (optional) is a type of string
  ucd_mode = var.ucd_mode
  # ucd_mode_group_mapping - (optional) is a type of string
  ucd_mode_group_mapping = var.ucd_mode_group_mapping
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "http_header_insertion" {
    for_each = var.http_header_insertion
    content {
      # domains - (optional) is a type of list of string
      domains = http_header_insertion.value["domains"]
      # name - (required) is a type of string
      name = http_header_insertion.value["name"]
      # type - (optional) is a type of string
      type = http_header_insertion.value["type"]

      dynamic "http_header" {
        for_each = http_header_insertion.value.http_header
        content {
          # header - (required) is a type of string
          header = http_header.value["header"]
          # log - (optional) is a type of bool
          log = http_header.value["log"]
          # value - (required) is a type of string
          value = http_header.value["value"]
        }
      }

    }
  }

  dynamic "machine_learning_model" {
    for_each = var.machine_learning_model
    content {
      # action - (required) is a type of string
      action = machine_learning_model.value["action"]
      # model - (required) is a type of string
      model = machine_learning_model.value["model"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_url_filtering_security_profile.this.id
}

output "this" {
  value = panos_url_filtering_security_profile.this
}
```

[top](#index)