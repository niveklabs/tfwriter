# alicloud_cms_monitor_group_instanceses

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
module "alicloud_cms_monitor_group_instanceses" {
  source = "./modules/alicloud/d/alicloud_cms_monitor_group_instanceses"

  # ids - (required) is a type of list of string
  ids = []
  # keyword - (optional) is a type of string
  keyword = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(required)"
  type        = list(string)
}

variable "keyword" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cms_monitor_group_instanceses" "this" {
  ids         = var.ids
  keyword     = var.keyword
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cms_monitor_group_instanceses.this.id
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_cms_monitor_group_instanceses.this.instances
}

output "this" {
  value = alicloud_cms_monitor_group_instanceses.this
}
```

[top](#index)