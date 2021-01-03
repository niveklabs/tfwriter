# azurerm_media_transform

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_media_transform" {
  source = "./modules/azurerm/r/azurerm_media_transform"

  # description - (optional) is a type of string
  description = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  output = [{
    audio_analyzer_preset = [{
      audio_analysis_mode = null
      audio_language      = null
    }]
    builtin_preset = [{
      preset_name = null
    }]
    face_detector_preset = [{
      analysis_resolution = null
    }]
    on_error_action   = null
    relative_priority = null
    video_analyzer_preset = [{
      audio_analysis_mode = null
      audio_language      = null
      insights_type       = null
    }]
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
variable "description" {
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

variable "output" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      audio_analyzer_preset = list(object(
        {
          audio_analysis_mode = string
          audio_language      = string
        }
      ))
      builtin_preset = list(object(
        {
          preset_name = string
        }
      ))
      face_detector_preset = list(object(
        {
          analysis_resolution = string
        }
      ))
      on_error_action   = string
      relative_priority = string
      video_analyzer_preset = list(object(
        {
          audio_analysis_mode = string
          audio_language      = string
          insights_type       = string
        }
      ))
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
resource "azurerm_media_transform" "this" {
  description                 = var.description
  media_services_account_name = var.media_services_account_name
  name                        = var.name
  resource_group_name         = var.resource_group_name

  dynamic "output" {
    for_each = var.output
    content {
      on_error_action   = output.value["on_error_action"]
      relative_priority = output.value["relative_priority"]

      dynamic "audio_analyzer_preset" {
        for_each = output.value.audio_analyzer_preset
        content {
          audio_analysis_mode = audio_analyzer_preset.value["audio_analysis_mode"]
          audio_language      = audio_analyzer_preset.value["audio_language"]
        }
      }

      dynamic "builtin_preset" {
        for_each = output.value.builtin_preset
        content {
          preset_name = builtin_preset.value["preset_name"]
        }
      }

      dynamic "face_detector_preset" {
        for_each = output.value.face_detector_preset
        content {
          analysis_resolution = face_detector_preset.value["analysis_resolution"]
        }
      }

      dynamic "video_analyzer_preset" {
        for_each = output.value.video_analyzer_preset
        content {
          audio_analysis_mode = video_analyzer_preset.value["audio_analysis_mode"]
          audio_language      = video_analyzer_preset.value["audio_language"]
          insights_type       = video_analyzer_preset.value["insights_type"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
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
  value       = azurerm_media_transform.this.id
}

output "this" {
  value = azurerm_media_transform.this
}
```

[top](#index)