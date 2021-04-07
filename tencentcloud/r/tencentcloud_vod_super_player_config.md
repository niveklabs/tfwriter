# tencentcloud_vod_super_player_config

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_vod_super_player_config" {
  source = "./modules/tencentcloud/r/tencentcloud_vod_super_player_config"

  # adaptive_dynamic_streaming_definition - (optional) is a type of string
  adaptive_dynamic_streaming_definition = null
  # comment - (optional) is a type of string
  comment = null
  # domain - (optional) is a type of string
  domain = null
  # drm_switch - (optional) is a type of bool
  drm_switch = null
  # image_sprite_definition - (optional) is a type of string
  image_sprite_definition = null
  # name - (required) is a type of string
  name = null
  # scheme - (optional) is a type of string
  scheme = null
  # sub_app_id - (optional) is a type of number
  sub_app_id = null

  drm_streaming_info = [{
    simple_aes_definition = null
  }]

  resolution_names = [{
    min_edge_length = null
    name            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "adaptive_dynamic_streaming_definition" {
  description = "(optional) - ID of the unencrypted adaptive bitrate streaming template that allows output, which is required if `drm_switch` is `false`."
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional) - Template description. Length limit: 256 characters."
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional) - Domain name used for playback. If it is left empty or set to `Default`, the domain name configured in [Default Distribution Configuration](https://cloud.tencent.com/document/product/266/33373) will be used. `Default` by default."
  type        = string
  default     = null
}

variable "drm_switch" {
  description = "(optional) - Switch of DRM-protected adaptive bitstream playback: `true`: enabled, indicating to play back only output adaptive bitstreams protected by DRM; `false`: disabled, indicating to play back unencrypted output adaptive bitstreams. Default value: `false`."
  type        = bool
  default     = null
}

variable "image_sprite_definition" {
  description = "(optional) - ID of the image sprite template that allows output."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Player configuration name, which can contain up to 64 letters, digits, underscores, and hyphens (such as test_ABC-123) and must be unique under a user."
  type        = string
}

variable "scheme" {
  description = "(optional) - Scheme used for playback. If it is left empty or set to `Default`, the scheme configured in [Default Distribution Configuration](https://cloud.tencent.com/document/product/266/33373) will be used. Other valid values: `HTTP`; `HTTPS`."
  type        = string
  default     = null
}

variable "sub_app_id" {
  description = "(optional) - Subapplication ID in VOD. If you need to access a resource in a subapplication, enter the subapplication ID in this field; otherwise, leave it empty."
  type        = number
  default     = null
}

variable "drm_streaming_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      simple_aes_definition = string
    }
  ))
  default = []
}

variable "resolution_names" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      min_edge_length = number
      name            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vod_super_player_config" "this" {
  # adaptive_dynamic_streaming_definition - (optional) is a type of string
  adaptive_dynamic_streaming_definition = var.adaptive_dynamic_streaming_definition
  # comment - (optional) is a type of string
  comment = var.comment
  # domain - (optional) is a type of string
  domain = var.domain
  # drm_switch - (optional) is a type of bool
  drm_switch = var.drm_switch
  # image_sprite_definition - (optional) is a type of string
  image_sprite_definition = var.image_sprite_definition
  # name - (required) is a type of string
  name = var.name
  # scheme - (optional) is a type of string
  scheme = var.scheme
  # sub_app_id - (optional) is a type of number
  sub_app_id = var.sub_app_id

  dynamic "drm_streaming_info" {
    for_each = var.drm_streaming_info
    content {
      # simple_aes_definition - (optional) is a type of string
      simple_aes_definition = drm_streaming_info.value["simple_aes_definition"]
    }
  }

  dynamic "resolution_names" {
    for_each = var.resolution_names
    content {
      # min_edge_length - (required) is a type of number
      min_edge_length = resolution_names.value["min_edge_length"]
      # name - (required) is a type of string
      name = resolution_names.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vod_super_player_config.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vod_super_player_config.this.id
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_vod_super_player_config.this.update_time
}

output "this" {
  value = tencentcloud_vod_super_player_config.this
}
```

[top](#index)