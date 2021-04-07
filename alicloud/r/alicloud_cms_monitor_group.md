# alicloud_cms_monitor_group

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "alicloud_cms_monitor_group" {
  source = "./modules/alicloud/r/alicloud_cms_monitor_group"

  # contact_groups - (optional) is a type of list of string
  contact_groups = []
  # monitor_group_name - (required) is a type of string
  monitor_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "contact_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "monitor_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cms_monitor_group" "this" {
  # contact_groups - (optional) is a type of list of string
  contact_groups = var.contact_groups
  # monitor_group_name - (required) is a type of string
  monitor_group_name = var.monitor_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cms_monitor_group.this.id
}

output "this" {
  value = alicloud_cms_monitor_group.this
}
```

[top](#index)