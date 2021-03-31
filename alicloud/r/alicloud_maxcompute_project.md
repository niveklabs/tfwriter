# alicloud_maxcompute_project

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_maxcompute_project" {
  source = "./modules/alicloud/r/alicloud_maxcompute_project"

  # name - (optional) is a type of string
  name = null
  # order_type - (required) is a type of string
  order_type = null
  # project_name - (optional) is a type of string
  project_name = null
  # specification_type - (required) is a type of string
  specification_type = null

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "order_type" {
  description = "(required)"
  type        = string
}

variable "project_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "specification_type" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_maxcompute_project" "this" {
  name               = var.name
  order_type         = var.order_type
  project_name       = var.project_name
  specification_type = var.specification_type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_maxcompute_project.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_maxcompute_project.this.name
}

output "project_name" {
  description = "returns a string"
  value       = alicloud_maxcompute_project.this.project_name
}

output "this" {
  value = alicloud_maxcompute_project.this
}
```

[top](#index)