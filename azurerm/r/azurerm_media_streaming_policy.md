# azurerm_media_streaming_policy

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
module "azurerm_media_streaming_policy" {
  source = "./modules/azurerm/r/azurerm_media_streaming_policy"

  # default_content_key_policy_name - (optional) is a type of string
  default_content_key_policy_name = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  common_encryption_cbcs = [{
    default_content_key = [{
      label       = null
      policy_name = null
    }]
    drm_fairplay = [{
      allow_persistent_license                = null
      custom_license_acquisition_url_template = null
    }]
    enabled_protocols = [{
      dash             = null
      download         = null
      hls              = null
      smooth_streaming = null
    }]
  }]

  common_encryption_cenc = [{
    default_content_key = [{
      label       = null
      policy_name = null
    }]
    drm_playready = [{
      custom_attributes                       = null
      custom_license_acquisition_url_template = null
    }]
    drm_widevine_custom_license_acquisition_url_template = null
    enabled_protocols = [{
      dash             = null
      download         = null
      hls              = null
      smooth_streaming = null
    }]
  }]

  no_encryption_enabled_protocols = [{
    dash             = null
    download         = null
    hls              = null
    smooth_streaming = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_content_key_policy_name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "common_encryption_cbcs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_content_key = list(object(
        {
          label       = string
          policy_name = string
        }
      ))
      drm_fairplay = list(object(
        {
          allow_persistent_license                = bool
          custom_license_acquisition_url_template = string
        }
      ))
      enabled_protocols = list(object(
        {
          dash             = bool
          download         = bool
          hls              = bool
          smooth_streaming = bool
        }
      ))
    }
  ))
  default = []
}

variable "common_encryption_cenc" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_content_key = list(object(
        {
          label       = string
          policy_name = string
        }
      ))
      drm_playready = list(object(
        {
          custom_attributes                       = string
          custom_license_acquisition_url_template = string
        }
      ))
      drm_widevine_custom_license_acquisition_url_template = string
      enabled_protocols = list(object(
        {
          dash             = bool
          download         = bool
          hls              = bool
          smooth_streaming = bool
        }
      ))
    }
  ))
  default = []
}

variable "no_encryption_enabled_protocols" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dash             = bool
      download         = bool
      hls              = bool
      smooth_streaming = bool
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_media_streaming_policy" "this" {
  default_content_key_policy_name = var.default_content_key_policy_name
  media_services_account_name     = var.media_services_account_name
  name                            = var.name
  resource_group_name             = var.resource_group_name

  dynamic "common_encryption_cbcs" {
    for_each = var.common_encryption_cbcs
    content {

      dynamic "default_content_key" {
        for_each = common_encryption_cbcs.value.default_content_key
        content {
          label       = default_content_key.value["label"]
          policy_name = default_content_key.value["policy_name"]
        }
      }

      dynamic "drm_fairplay" {
        for_each = common_encryption_cbcs.value.drm_fairplay
        content {
          allow_persistent_license                = drm_fairplay.value["allow_persistent_license"]
          custom_license_acquisition_url_template = drm_fairplay.value["custom_license_acquisition_url_template"]
        }
      }

      dynamic "enabled_protocols" {
        for_each = common_encryption_cbcs.value.enabled_protocols
        content {
          dash             = enabled_protocols.value["dash"]
          download         = enabled_protocols.value["download"]
          hls              = enabled_protocols.value["hls"]
          smooth_streaming = enabled_protocols.value["smooth_streaming"]
        }
      }

    }
  }

  dynamic "common_encryption_cenc" {
    for_each = var.common_encryption_cenc
    content {
      drm_widevine_custom_license_acquisition_url_template = common_encryption_cenc.value["drm_widevine_custom_license_acquisition_url_template"]

      dynamic "default_content_key" {
        for_each = common_encryption_cenc.value.default_content_key
        content {
          label       = default_content_key.value["label"]
          policy_name = default_content_key.value["policy_name"]
        }
      }

      dynamic "drm_playready" {
        for_each = common_encryption_cenc.value.drm_playready
        content {
          custom_attributes                       = drm_playready.value["custom_attributes"]
          custom_license_acquisition_url_template = drm_playready.value["custom_license_acquisition_url_template"]
        }
      }

      dynamic "enabled_protocols" {
        for_each = common_encryption_cenc.value.enabled_protocols
        content {
          dash             = enabled_protocols.value["dash"]
          download         = enabled_protocols.value["download"]
          hls              = enabled_protocols.value["hls"]
          smooth_streaming = enabled_protocols.value["smooth_streaming"]
        }
      }

    }
  }

  dynamic "no_encryption_enabled_protocols" {
    for_each = var.no_encryption_enabled_protocols
    content {
      dash             = no_encryption_enabled_protocols.value["dash"]
      download         = no_encryption_enabled_protocols.value["download"]
      hls              = no_encryption_enabled_protocols.value["hls"]
      smooth_streaming = no_encryption_enabled_protocols.value["smooth_streaming"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_media_streaming_policy.this.id
}

output "this" {
  value = azurerm_media_streaming_policy.this
}
```

[top](#index)