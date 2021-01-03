# alicloud_nas_access_group

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_nas_access_group" {
  source = "./modules/alicloud/r/alicloud_nas_access_group"

  # access_group_name - (optional) is a type of string
  access_group_name = null
  # access_group_type - (optional) is a type of string
  access_group_type = null
  # description - (optional) is a type of string
  description = null
  # file_system_type - (optional) is a type of string
  file_system_type = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_system_type" {
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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_nas_access_group" "this" {
  access_group_name = var.access_group_name
  access_group_type = var.access_group_type
  description       = var.description
  file_system_type  = var.file_system_type
  name              = var.name
  type              = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_group_name" {
  description = "returns a string"
  value       = alicloud_nas_access_group.this.access_group_name
}

output "access_group_type" {
  description = "returns a string"
  value       = alicloud_nas_access_group.this.access_group_type
}

output "id" {
  description = "returns a string"
  value       = alicloud_nas_access_group.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_nas_access_group.this.name
}

output "type" {
  description = "returns a string"
  value       = alicloud_nas_access_group.this.type
}

output "this" {
  value = alicloud_nas_access_group.this
}
```

[top](#index)