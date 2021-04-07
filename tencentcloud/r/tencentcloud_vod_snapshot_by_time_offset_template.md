# tencentcloud_vod_snapshot_by_time_offset_template

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
module "tencentcloud_vod_snapshot_by_time_offset_template" {
  source = "./modules/tencentcloud/r/tencentcloud_vod_snapshot_by_time_offset_template"

  # comment - (optional) is a type of string
  comment = null
  # fill_type - (optional) is a type of string
  fill_type = null
  # format - (optional) is a type of string
  format = null
  # height - (optional) is a type of number
  height = null
  # name - (required) is a type of string
  name = null
  # resolution_adaptive - (optional) is a type of bool
  resolution_adaptive = null
  # sub_app_id - (optional) is a type of number
  sub_app_id = null
  # width - (optional) is a type of number
  width = null
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

variable "fill_type" {
  description = "(optional) - Fill refers to the way of processing a screenshot when its aspect ratio is different from that of the source video. The following fill types are supported: `stretch`: stretch. The screenshot will be stretched frame by frame to match the aspect ratio of the source video, which may make the screenshot `shorter` or `longer`; `black`: fill with black. This option retains the aspect ratio of the source video for the screenshot and fills the unmatched area with black color blocks. `white`: fill with white. This option retains the aspect ratio of the source video for the screenshot and fills the unmatched area with white color blocks. `gauss`: fill with Gaussian blur. This option retains the aspect ratio of the source video for the screenshot and fills the unmatched area with Gaussian blur. Default value: `black`."
  type        = string
  default     = null
}

variable "format" {
  description = "(optional) - Image format. Valid values: `jpg`, `png`. Default value: `jpg`."
  type        = string
  default     = null
}

variable "height" {
  description = "(optional) - Maximum value of the `height` (or short side) of a screenshot in px. Value range: 0 and [128, 4,096]. If both `width` and `height` are `0`, the resolution will be the same as that of the source video; If `width` is `0`, but `height` is not `0`, `width` will be proportionally scaled; If `width` is not `0`, but `height` is `0`, `height` will be proportionally scaled; If both `width` and `height` are not `0`, the custom resolution will be used. Default value: `0`."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of a time point screen capturing template. Length limit: 64 characters."
  type        = string
}

variable "resolution_adaptive" {
  description = "(optional) - Resolution adaption. Valid values: `true`,`false`. `true`: enabled. In this case, `width` represents the long side of a video, while `height` the short side; `false`: disabled. In this case, `width` represents the width of a video, while `height` the height. Default value: `true`."
  type        = bool
  default     = null
}

variable "sub_app_id" {
  description = "(optional) - Subapplication ID in VOD. If you need to access a resource in a subapplication, enter the subapplication ID in this field; otherwise, leave it empty."
  type        = number
  default     = null
}

variable "width" {
  description = "(optional) - Maximum value of the `width` (or long side) of a screenshot in px. Value range: 0 and [128, 4,096]. If both `width` and `height` are `0`, the resolution will be the same as that of the source video; If `width` is `0`, but `height` is not `0`, width will be proportionally scaled; If `width` is not `0`, but `height` is `0`, `height` will be proportionally scaled; If both `width` and `height` are not `0`, the custom resolution will be used. Default value: `0`."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vod_snapshot_by_time_offset_template" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # fill_type - (optional) is a type of string
  fill_type = var.fill_type
  # format - (optional) is a type of string
  format = var.format
  # height - (optional) is a type of number
  height = var.height
  # name - (required) is a type of string
  name = var.name
  # resolution_adaptive - (optional) is a type of bool
  resolution_adaptive = var.resolution_adaptive
  # sub_app_id - (optional) is a type of number
  sub_app_id = var.sub_app_id
  # width - (optional) is a type of number
  width = var.width
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vod_snapshot_by_time_offset_template.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vod_snapshot_by_time_offset_template.this.id
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_vod_snapshot_by_time_offset_template.this.update_time
}

output "this" {
  value = tencentcloud_vod_snapshot_by_time_offset_template.this
}
```

[top](#index)