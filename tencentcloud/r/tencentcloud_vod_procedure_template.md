# tencentcloud_vod_procedure_template

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
module "tencentcloud_vod_procedure_template" {
  source = "./modules/tencentcloud/r/tencentcloud_vod_procedure_template"

  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null
  # sub_app_id - (optional) is a type of number
  sub_app_id = null

  media_process_task = [{
    adaptive_dynamic_streaming_task_list = [{
      definition = null
      watermark_list = [{
        definition        = null
        end_time_offset   = null
        start_time_offset = null
        svg_content       = null
        text_content      = null
      }]
    }]
    animated_graphic_task_list = [{
      definition        = null
      end_time_offset   = null
      start_time_offset = null
    }]
    cover_by_snapshot_task_list = [{
      definition     = null
      position_type  = null
      position_value = null
      watermark_list = [{
        definition        = null
        end_time_offset   = null
        start_time_offset = null
        svg_content       = null
        text_content      = null
      }]
    }]
    image_sprite_task_list = [{
      definition = null
    }]
    sample_snapshot_task_list = [{
      definition = null
      watermark_list = [{
        definition        = null
        end_time_offset   = null
        start_time_offset = null
        svg_content       = null
        text_content      = null
      }]
    }]
    snapshot_by_time_offset_task_list = [{
      definition           = null
      ext_time_offset_list = []
      watermark_list = [{
        definition        = null
        end_time_offset   = null
        start_time_offset = null
        svg_content       = null
        text_content      = null
      }]
    }]
    transcode_task_list = [{
      definition = null
      mosaic_list = [{
        coordinate_origin = null
        end_time_offset   = null
        height            = null
        start_time_offset = null
        width             = null
        x_pos             = null
        y_pos             = null
      }]
      watermark_list = [{
        definition        = null
        end_time_offset   = null
        start_time_offset = null
        svg_content       = null
        text_content      = null
      }]
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

variable "name" {
  description = "(required) - Task flow name (up to 20 characters)."
  type        = string
}

variable "sub_app_id" {
  description = "(optional) - Subapplication ID in VOD. If you need to access a resource in a subapplication, enter the subapplication ID in this field; otherwise, leave it empty."
  type        = number
  default     = null
}

variable "media_process_task" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      adaptive_dynamic_streaming_task_list = list(object(
        {
          definition = string
          watermark_list = list(object(
            {
              definition        = string
              end_time_offset   = number
              start_time_offset = number
              svg_content       = string
              text_content      = string
            }
          ))
        }
      ))
      animated_graphic_task_list = list(object(
        {
          definition        = string
          end_time_offset   = number
          start_time_offset = number
        }
      ))
      cover_by_snapshot_task_list = list(object(
        {
          definition     = string
          position_type  = string
          position_value = number
          watermark_list = list(object(
            {
              definition        = string
              end_time_offset   = number
              start_time_offset = number
              svg_content       = string
              text_content      = string
            }
          ))
        }
      ))
      image_sprite_task_list = list(object(
        {
          definition = string
        }
      ))
      sample_snapshot_task_list = list(object(
        {
          definition = string
          watermark_list = list(object(
            {
              definition        = string
              end_time_offset   = number
              start_time_offset = number
              svg_content       = string
              text_content      = string
            }
          ))
        }
      ))
      snapshot_by_time_offset_task_list = list(object(
        {
          definition           = string
          ext_time_offset_list = list(string)
          watermark_list = list(object(
            {
              definition        = string
              end_time_offset   = number
              start_time_offset = number
              svg_content       = string
              text_content      = string
            }
          ))
        }
      ))
      transcode_task_list = list(object(
        {
          definition = string
          mosaic_list = list(object(
            {
              coordinate_origin = string
              end_time_offset   = number
              height            = string
              start_time_offset = number
              width             = string
              x_pos             = string
              y_pos             = string
            }
          ))
          watermark_list = list(object(
            {
              definition        = string
              end_time_offset   = number
              start_time_offset = number
              svg_content       = string
              text_content      = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vod_procedure_template" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # name - (required) is a type of string
  name = var.name
  # sub_app_id - (optional) is a type of number
  sub_app_id = var.sub_app_id

  dynamic "media_process_task" {
    for_each = var.media_process_task
    content {

      dynamic "adaptive_dynamic_streaming_task_list" {
        for_each = media_process_task.value.adaptive_dynamic_streaming_task_list
        content {
          # definition - (required) is a type of string
          definition = adaptive_dynamic_streaming_task_list.value["definition"]

          dynamic "watermark_list" {
            for_each = adaptive_dynamic_streaming_task_list.value.watermark_list
            content {
              # definition - (required) is a type of string
              definition = watermark_list.value["definition"]
              # end_time_offset - (optional) is a type of number
              end_time_offset = watermark_list.value["end_time_offset"]
              # start_time_offset - (optional) is a type of number
              start_time_offset = watermark_list.value["start_time_offset"]
              # svg_content - (optional) is a type of string
              svg_content = watermark_list.value["svg_content"]
              # text_content - (optional) is a type of string
              text_content = watermark_list.value["text_content"]
            }
          }

        }
      }

      dynamic "animated_graphic_task_list" {
        for_each = media_process_task.value.animated_graphic_task_list
        content {
          # definition - (required) is a type of string
          definition = animated_graphic_task_list.value["definition"]
          # end_time_offset - (required) is a type of number
          end_time_offset = animated_graphic_task_list.value["end_time_offset"]
          # start_time_offset - (required) is a type of number
          start_time_offset = animated_graphic_task_list.value["start_time_offset"]
        }
      }

      dynamic "cover_by_snapshot_task_list" {
        for_each = media_process_task.value.cover_by_snapshot_task_list
        content {
          # definition - (required) is a type of string
          definition = cover_by_snapshot_task_list.value["definition"]
          # position_type - (required) is a type of string
          position_type = cover_by_snapshot_task_list.value["position_type"]
          # position_value - (required) is a type of number
          position_value = cover_by_snapshot_task_list.value["position_value"]

          dynamic "watermark_list" {
            for_each = cover_by_snapshot_task_list.value.watermark_list
            content {
              # definition - (required) is a type of string
              definition = watermark_list.value["definition"]
              # end_time_offset - (optional) is a type of number
              end_time_offset = watermark_list.value["end_time_offset"]
              # start_time_offset - (optional) is a type of number
              start_time_offset = watermark_list.value["start_time_offset"]
              # svg_content - (optional) is a type of string
              svg_content = watermark_list.value["svg_content"]
              # text_content - (optional) is a type of string
              text_content = watermark_list.value["text_content"]
            }
          }

        }
      }

      dynamic "image_sprite_task_list" {
        for_each = media_process_task.value.image_sprite_task_list
        content {
          # definition - (required) is a type of string
          definition = image_sprite_task_list.value["definition"]
        }
      }

      dynamic "sample_snapshot_task_list" {
        for_each = media_process_task.value.sample_snapshot_task_list
        content {
          # definition - (required) is a type of string
          definition = sample_snapshot_task_list.value["definition"]

          dynamic "watermark_list" {
            for_each = sample_snapshot_task_list.value.watermark_list
            content {
              # definition - (required) is a type of string
              definition = watermark_list.value["definition"]
              # end_time_offset - (optional) is a type of number
              end_time_offset = watermark_list.value["end_time_offset"]
              # start_time_offset - (optional) is a type of number
              start_time_offset = watermark_list.value["start_time_offset"]
              # svg_content - (optional) is a type of string
              svg_content = watermark_list.value["svg_content"]
              # text_content - (optional) is a type of string
              text_content = watermark_list.value["text_content"]
            }
          }

        }
      }

      dynamic "snapshot_by_time_offset_task_list" {
        for_each = media_process_task.value.snapshot_by_time_offset_task_list
        content {
          # definition - (required) is a type of string
          definition = snapshot_by_time_offset_task_list.value["definition"]
          # ext_time_offset_list - (optional) is a type of list of string
          ext_time_offset_list = snapshot_by_time_offset_task_list.value["ext_time_offset_list"]

          dynamic "watermark_list" {
            for_each = snapshot_by_time_offset_task_list.value.watermark_list
            content {
              # definition - (required) is a type of string
              definition = watermark_list.value["definition"]
              # end_time_offset - (optional) is a type of number
              end_time_offset = watermark_list.value["end_time_offset"]
              # start_time_offset - (optional) is a type of number
              start_time_offset = watermark_list.value["start_time_offset"]
              # svg_content - (optional) is a type of string
              svg_content = watermark_list.value["svg_content"]
              # text_content - (optional) is a type of string
              text_content = watermark_list.value["text_content"]
            }
          }

        }
      }

      dynamic "transcode_task_list" {
        for_each = media_process_task.value.transcode_task_list
        content {
          # definition - (required) is a type of string
          definition = transcode_task_list.value["definition"]

          dynamic "mosaic_list" {
            for_each = transcode_task_list.value.mosaic_list
            content {
              # coordinate_origin - (optional) is a type of string
              coordinate_origin = mosaic_list.value["coordinate_origin"]
              # end_time_offset - (optional) is a type of number
              end_time_offset = mosaic_list.value["end_time_offset"]
              # height - (optional) is a type of string
              height = mosaic_list.value["height"]
              # start_time_offset - (optional) is a type of number
              start_time_offset = mosaic_list.value["start_time_offset"]
              # width - (optional) is a type of string
              width = mosaic_list.value["width"]
              # x_pos - (optional) is a type of string
              x_pos = mosaic_list.value["x_pos"]
              # y_pos - (optional) is a type of string
              y_pos = mosaic_list.value["y_pos"]
            }
          }

          dynamic "watermark_list" {
            for_each = transcode_task_list.value.watermark_list
            content {
              # definition - (required) is a type of string
              definition = watermark_list.value["definition"]
              # end_time_offset - (optional) is a type of number
              end_time_offset = watermark_list.value["end_time_offset"]
              # start_time_offset - (optional) is a type of number
              start_time_offset = watermark_list.value["start_time_offset"]
              # svg_content - (optional) is a type of string
              svg_content = watermark_list.value["svg_content"]
              # text_content - (optional) is a type of string
              text_content = watermark_list.value["text_content"]
            }
          }

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
  value       = tencentcloud_vod_procedure_template.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vod_procedure_template.this.id
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_vod_procedure_template.this.update_time
}

output "this" {
  value = tencentcloud_vod_procedure_template.this
}
```

[top](#index)