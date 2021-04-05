# alicloud_ecs_launch_templates

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ecs_launch_templates" {
  source = "./modules/alicloud/d/alicloud_ecs_launch_templates"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # launch_template_name - (optional) is a type of string
  launch_template_name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # template_resource_group_id - (optional) is a type of string
  template_resource_group_id = null
  # template_tags - (optional) is a type of map of string
  template_tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "launch_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ecs_launch_templates" "this" {
  enable_details             = var.enable_details
  ids                        = var.ids
  launch_template_name       = var.launch_template_name
  name_regex                 = var.name_regex
  output_file                = var.output_file
  template_resource_group_id = var.template_resource_group_id
  template_tags              = var.template_tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ecs_launch_templates.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_launch_templates.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_launch_templates.this.names
}

output "templates" {
  description = "returns a list of object"
  value       = data.alicloud_ecs_launch_templates.this.templates
}

output "this" {
  value = alicloud_ecs_launch_templates.this
}
```

[top](#index)