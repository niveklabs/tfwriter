# tencentcloud_vod_adaptive_dynamic_streaming_template

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
module "tencentcloud_vod_adaptive_dynamic_streaming_template" {
  source = "./modules/tencentcloud/r/tencentcloud_vod_adaptive_dynamic_streaming_template"

  # comment - (optional) is a type of string
  comment = null
  # disable_higher_video_bitrate - (optional) is a type of bool
  disable_higher_video_bitrate = null
  # disable_higher_video_resolution - (optional) is a type of bool
  disable_higher_video_resolution = null
  # drm_type - (optional) is a type of string
  drm_type = null
  # format - (required) is a type of string
  format = null
  # name - (required) is a type of string
  name = null
  # sub_app_id - (optional) is a type of number
  sub_app_id = null

  stream_info = [{
    audio = [{
      audio_channel = null
      bitrate       = null
      codec         = null
      sample_rate   = null
    }]
    remove_audio = null
    video = [{
      bitrate             = null
      codec               = null
      fill_type           = null
      fps                 = null
      height              = null
      resolution_adaptive = null
      width               = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional) - Template description. Length limit: 256 characters."
  type        = string
  default     = null
}

variable "disable_higher_video_bitrate" {
  description = "(optional) - Whether to prohibit transcoding video from low bitrate to high bitrate. Valid values: `false`,`true`. `false`: no, `true`: yes. Default value: `false`."
  type        = bool
  default     = null
}

variable "disable_higher_video_resolution" {
  description = "(optional) - Whether to prohibit transcoding from low resolution to high resolution. Valid values: `false`,`true`. `false`: no, `true`: yes. Default value: `false`."
  type        = bool
  default     = null
}

variable "drm_type" {
  description = "(optional) - DRM scheme type. Valid values: `SimpleAES`. If this field is an empty string, DRM will not be performed on the video."
  type        = string
  default     = null
}

variable "format" {
  description = "(required) - Adaptive bitstream format. Valid values: `HLS`."
  type        = string
}

variable "name" {
  description = "(required) - Template name. Length limit: 64 characters."
  type        = string
}

variable "sub_app_id" {
  description = "(optional) - Subapplication ID in VOD. If you need to access a resource in a subapplication, enter the subapplication ID in this field; otherwise, leave it empty."
  type        = number
  default     = null
}

variable "stream_info" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      audio = list(object(
        {
          audio_channel = string
          bitrate       = number
          codec         = string
          sample_rate   = number
        }
      ))
      remove_audio = bool
      video = list(object(
        {
          bitrate             = number
          codec               = string
          fill_type           = string
          fps                 = number
          height              = number
          resolution_adaptive = bool
          width               = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vod_adaptive_dynamic_streaming_template" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # disable_higher_video_bitrate - (optional) is a type of bool
  disable_higher_video_bitrate = var.disable_higher_video_bitrate
  # disable_higher_video_resolution - (optional) is a type of bool
  disable_higher_video_resolution = var.disable_higher_video_resolution
  # drm_type - (optional) is a type of string
  drm_type = var.drm_type
  # format - (required) is a type of string
  format = var.format
  # name - (required) is a type of string
  name = var.name
  # sub_app_id - (optional) is a type of number
  sub_app_id = var.sub_app_id

  dynamic "stream_info" {
    for_each = var.stream_info
    content {
      # remove_audio - (optional) is a type of bool
      remove_audio = stream_info.value["remove_audio"]

      dynamic "audio" {
        for_each = stream_info.value.audio
        content {
          # audio_channel - (optional) is a type of string
          audio_channel = audio.value["audio_channel"]
          # bitrate - (required) is a type of number
          bitrate = audio.value["bitrate"]
          # codec - (required) is a type of string
          codec = audio.value["codec"]
          # sample_rate - (required) is a type of number
          sample_rate = audio.value["sample_rate"]
        }
      }

      dynamic "video" {
        for_each = stream_info.value.video
        content {
          # bitrate - (required) is a type of number
          bitrate = video.value["bitrate"]
          # codec - (required) is a type of string
          codec = video.value["codec"]
          # fill_type - (optional) is a type of string
          fill_type = video.value["fill_type"]
          # fps - (required) is a type of number
          fps = video.value["fps"]
          # height - (optional) is a type of number
          height = video.value["height"]
          # resolution_adaptive - (optional) is a type of bool
          resolution_adaptive = video.value["resolution_adaptive"]
          # width - (optional) is a type of number
          width = video.value["width"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vod_adaptive_dynamic_streaming_template.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vod_adaptive_dynamic_streaming_template.this.id
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_vod_adaptive_dynamic_streaming_template.this.update_time
}

output "this" {
  value = tencentcloud_vod_adaptive_dynamic_streaming_template.this
}
```

[top](#index)