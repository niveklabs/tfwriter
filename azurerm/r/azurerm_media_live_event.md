# azurerm_media_live_event

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_media_live_event" {
  source = "./modules/azurerm/r/azurerm_media_live_event"

  # auto_start_enabled - (optional) is a type of bool
  auto_start_enabled = null
  # description - (optional) is a type of string
  description = null
  # hostname_prefix - (optional) is a type of string
  hostname_prefix = null
  # location - (required) is a type of string
  location = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # transcription_languages - (optional) is a type of list of string
  transcription_languages = []
  # use_static_hostname - (optional) is a type of bool
  use_static_hostname = null

  cross_site_access_policy = [{
    client_access_policy = null
    cross_domain_policy  = null
  }]

  encoding = [{
    key_frame_interval = null
    preset_name        = null
    stretch_mode       = null
    type               = null
  }]

  input = [{
    access_token = null
    endpoint = [{
      protocol = null
      url      = null
    }]
    ip_access_control_allow = [{
      address              = null
      name                 = null
      subnet_prefix_length = null
    }]
    key_frame_interval_duration = null
    streaming_protocol          = null
  }]

  preview = [{
    alternative_media_id = null
    endpoint = [{
      protocol = null
      url      = null
    }]
    ip_access_control_allow = [{
      address              = null
      name                 = null
      subnet_prefix_length = null
    }]
    preview_locator       = null
    streaming_policy_name = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_start_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "media_services_account_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transcription_languages" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "use_static_hostname" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cross_site_access_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_access_policy = string
      cross_domain_policy  = string
    }
  ))
  default = []
}

variable "encoding" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      key_frame_interval = string
      preset_name        = string
      stretch_mode       = string
      type               = string
    }
  ))
  default = []
}

variable "input" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      access_token = string
      endpoint = list(object(
        {
          protocol = string
          url      = string
        }
      ))
      ip_access_control_allow = list(object(
        {
          address              = string
          name                 = string
          subnet_prefix_length = number
        }
      ))
      key_frame_interval_duration = string
      streaming_protocol          = string
    }
  ))
}

variable "preview" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      alternative_media_id = string
      endpoint = list(object(
        {
          protocol = string
          url      = string
        }
      ))
      ip_access_control_allow = list(object(
        {
          address              = string
          name                 = string
          subnet_prefix_length = number
        }
      ))
      preview_locator       = string
      streaming_policy_name = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_media_live_event" "this" {
  # auto_start_enabled - (optional) is a type of bool
  auto_start_enabled = var.auto_start_enabled
  # description - (optional) is a type of string
  description = var.description
  # hostname_prefix - (optional) is a type of string
  hostname_prefix = var.hostname_prefix
  # location - (required) is a type of string
  location = var.location
  # media_services_account_name - (required) is a type of string
  media_services_account_name = var.media_services_account_name
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # transcription_languages - (optional) is a type of list of string
  transcription_languages = var.transcription_languages
  # use_static_hostname - (optional) is a type of bool
  use_static_hostname = var.use_static_hostname

  dynamic "cross_site_access_policy" {
    for_each = var.cross_site_access_policy
    content {
      # client_access_policy - (optional) is a type of string
      client_access_policy = cross_site_access_policy.value["client_access_policy"]
      # cross_domain_policy - (optional) is a type of string
      cross_domain_policy = cross_site_access_policy.value["cross_domain_policy"]
    }
  }

  dynamic "encoding" {
    for_each = var.encoding
    content {
      # key_frame_interval - (optional) is a type of string
      key_frame_interval = encoding.value["key_frame_interval"]
      # preset_name - (optional) is a type of string
      preset_name = encoding.value["preset_name"]
      # stretch_mode - (optional) is a type of string
      stretch_mode = encoding.value["stretch_mode"]
      # type - (optional) is a type of string
      type = encoding.value["type"]
    }
  }

  dynamic "input" {
    for_each = var.input
    content {
      # access_token - (optional) is a type of string
      access_token = input.value["access_token"]
      # key_frame_interval_duration - (optional) is a type of string
      key_frame_interval_duration = input.value["key_frame_interval_duration"]
      # streaming_protocol - (optional) is a type of string
      streaming_protocol = input.value["streaming_protocol"]

      dynamic "ip_access_control_allow" {
        for_each = input.value.ip_access_control_allow
        content {
          # address - (optional) is a type of string
          address = ip_access_control_allow.value["address"]
          # name - (optional) is a type of string
          name = ip_access_control_allow.value["name"]
          # subnet_prefix_length - (optional) is a type of number
          subnet_prefix_length = ip_access_control_allow.value["subnet_prefix_length"]
        }
      }

    }
  }

  dynamic "preview" {
    for_each = var.preview
    content {
      # alternative_media_id - (optional) is a type of string
      alternative_media_id = preview.value["alternative_media_id"]
      # preview_locator - (optional) is a type of string
      preview_locator = preview.value["preview_locator"]
      # streaming_policy_name - (optional) is a type of string
      streaming_policy_name = preview.value["streaming_policy_name"]

      dynamic "ip_access_control_allow" {
        for_each = preview.value.ip_access_control_allow
        content {
          # address - (optional) is a type of string
          address = ip_access_control_allow.value["address"]
          # name - (optional) is a type of string
          name = ip_access_control_allow.value["name"]
          # subnet_prefix_length - (optional) is a type of number
          subnet_prefix_length = ip_access_control_allow.value["subnet_prefix_length"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_media_live_event.this.id
}

output "this" {
  value = azurerm_media_live_event.this
}
```

[top](#index)