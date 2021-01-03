# alicloud_disks

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_disks" {
  source = "./modules/alicloud/d/alicloud_disks"

  # category - (optional) is a type of string
  category = null
  # encrypted - (optional) is a type of string
  encrypted = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (optional) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_id" {
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

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_disks" "this" {
  category          = var.category
  encrypted         = var.encrypted
  ids               = var.ids
  instance_id       = var.instance_id
  name_regex        = var.name_regex
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
  tags              = var.tags
  type              = var.type
}
```

[top](#index)

### Outputs

```terraform
output "disks" {
  description = "returns a list of object"
  value       = data.alicloud_disks.this.disks
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_disks.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_disks.this.ids
}

output "this" {
  value = alicloud_disks.this
}
```

[top](#index)