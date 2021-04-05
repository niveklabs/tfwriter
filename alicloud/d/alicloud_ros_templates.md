# alicloud_ros_templates

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
module "alicloud_ros_templates" {
  source = "./modules/alicloud/d/alicloud_ros_templates"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # share_type - (optional) is a type of string
  share_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_name - (optional) is a type of string
  template_name = null
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

variable "share_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ros_templates" "this" {
  enable_details = var.enable_details
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
  share_type     = var.share_type
  tags           = var.tags
  template_name  = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ros_templates.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ros_templates.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ros_templates.this.names
}

output "templates" {
  description = "returns a list of object"
  value       = data.alicloud_ros_templates.this.templates
}

output "this" {
  value = alicloud_ros_templates.this
}
```

[top](#index)