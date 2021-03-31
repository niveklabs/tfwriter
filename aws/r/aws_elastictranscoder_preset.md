# aws_elastictranscoder_preset

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_elastictranscoder_preset" {
  source = "./modules/aws/r/aws_elastictranscoder_preset"

  # container - (required) is a type of string
  container = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
  # video_codec_options - (optional) is a type of map of string
  video_codec_options = {}

  audio = [{
    audio_packing_mode = null
    bit_rate           = null
    channels           = null
    codec              = null
    sample_rate        = null
  }]

  audio_codec_options = [{
    bit_depth = null
    bit_order = null
    profile   = null
    signed    = null
  }]

  thumbnails = [{
    aspect_ratio   = null
    format         = null
    interval       = null
    max_height     = null
    max_width      = null
    padding_policy = null
    resolution     = null
    sizing_policy  = null
  }]

  video = [{
    aspect_ratio         = null
    bit_rate             = null
    codec                = null
    display_aspect_ratio = null
    fixed_gop            = null
    frame_rate           = null
    keyframes_max_dist   = null
    max_frame_rate       = null
    max_height           = null
    max_width            = null
    padding_policy       = null
    resolution           = null
    sizing_policy        = null
  }]

  video_watermarks = [{
    horizontal_align  = null
    horizontal_offset = null
    id                = null
    max_height        = null
    max_width         = null
    opacity           = null
    sizing_policy     = null
    target            = null
    vertical_align    = null
    vertical_offset   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "container" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "video_codec_options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "audio" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audio_packing_mode = string
      bit_rate           = string
      channels           = string
      codec              = string
      sample_rate        = string
    }
  ))
  default = []
}

variable "audio_codec_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bit_depth = string
      bit_order = string
      profile   = string
      signed    = string
    }
  ))
  default = []
}

variable "thumbnails" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aspect_ratio   = string
      format         = string
      interval       = string
      max_height     = string
      max_width      = string
      padding_policy = string
      resolution     = string
      sizing_policy  = string
    }
  ))
  default = []
}

variable "video" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aspect_ratio         = string
      bit_rate             = string
      codec                = string
      display_aspect_ratio = string
      fixed_gop            = string
      frame_rate           = string
      keyframes_max_dist   = string
      max_frame_rate       = string
      max_height           = string
      max_width            = string
      padding_policy       = string
      resolution           = string
      sizing_policy        = string
    }
  ))
  default = []
}

variable "video_watermarks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      horizontal_align  = string
      horizontal_offset = string
      id                = string
      max_height        = string
      max_width         = string
      opacity           = string
      sizing_policy     = string
      target            = string
      vertical_align    = string
      vertical_offset   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_elastictranscoder_preset" "this" {
  container           = var.container
  description         = var.description
  name                = var.name
  type                = var.type
  video_codec_options = var.video_codec_options

  dynamic "audio" {
    for_each = var.audio
    content {
      audio_packing_mode = audio.value["audio_packing_mode"]
      bit_rate           = audio.value["bit_rate"]
      channels           = audio.value["channels"]
      codec              = audio.value["codec"]
      sample_rate        = audio.value["sample_rate"]
    }
  }

  dynamic "audio_codec_options" {
    for_each = var.audio_codec_options
    content {
      bit_depth = audio_codec_options.value["bit_depth"]
      bit_order = audio_codec_options.value["bit_order"]
      profile   = audio_codec_options.value["profile"]
      signed    = audio_codec_options.value["signed"]
    }
  }

  dynamic "thumbnails" {
    for_each = var.thumbnails
    content {
      aspect_ratio   = thumbnails.value["aspect_ratio"]
      format         = thumbnails.value["format"]
      interval       = thumbnails.value["interval"]
      max_height     = thumbnails.value["max_height"]
      max_width      = thumbnails.value["max_width"]
      padding_policy = thumbnails.value["padding_policy"]
      resolution     = thumbnails.value["resolution"]
      sizing_policy  = thumbnails.value["sizing_policy"]
    }
  }

  dynamic "video" {
    for_each = var.video
    content {
      aspect_ratio         = video.value["aspect_ratio"]
      bit_rate             = video.value["bit_rate"]
      codec                = video.value["codec"]
      display_aspect_ratio = video.value["display_aspect_ratio"]
      fixed_gop            = video.value["fixed_gop"]
      frame_rate           = video.value["frame_rate"]
      keyframes_max_dist   = video.value["keyframes_max_dist"]
      max_frame_rate       = video.value["max_frame_rate"]
      max_height           = video.value["max_height"]
      max_width            = video.value["max_width"]
      padding_policy       = video.value["padding_policy"]
      resolution           = video.value["resolution"]
      sizing_policy        = video.value["sizing_policy"]
    }
  }

  dynamic "video_watermarks" {
    for_each = var.video_watermarks
    content {
      horizontal_align  = video_watermarks.value["horizontal_align"]
      horizontal_offset = video_watermarks.value["horizontal_offset"]
      id                = video_watermarks.value["id"]
      max_height        = video_watermarks.value["max_height"]
      max_width         = video_watermarks.value["max_width"]
      opacity           = video_watermarks.value["opacity"]
      sizing_policy     = video_watermarks.value["sizing_policy"]
      target            = video_watermarks.value["target"]
      vertical_align    = video_watermarks.value["vertical_align"]
      vertical_offset   = video_watermarks.value["vertical_offset"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_elastictranscoder_preset.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_elastictranscoder_preset.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_elastictranscoder_preset.this.name
}

output "type" {
  description = "returns a string"
  value       = aws_elastictranscoder_preset.this.type
}

output "this" {
  value = aws_elastictranscoder_preset.this
}
```

[top](#index)