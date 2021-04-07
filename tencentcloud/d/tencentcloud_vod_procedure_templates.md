# tencentcloud_vod_procedure_templates

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_vod_procedure_templates" {
  source = "./modules/tencentcloud/d/tencentcloud_vod_procedure_templates"

  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # sub_app_id - (optional) is a type of number
  sub_app_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of procedure template."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "sub_app_id" {
  description = "(optional) - Subapplication ID in VOD. If you need to access a resource in a subapplication, enter the subapplication ID in this field; otherwise, leave it empty."
  type        = number
  default     = null
}

variable "type" {
  description = "(optional) - Template type filter. Valid values: `Preset`, `Custom`. `Preset`: preset template; `Custom`: custom template."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vod_procedure_templates" "this" {
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # sub_app_id - (optional) is a type of number
  sub_app_id = var.sub_app_id
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vod_procedure_templates.this.id
}

output "template_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vod_procedure_templates.this.template_list
}

output "this" {
  value = tencentcloud_vod_procedure_templates.this
}
```

[top](#index)