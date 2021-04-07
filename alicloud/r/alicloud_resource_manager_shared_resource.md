# alicloud_resource_manager_shared_resource

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
module "alicloud_resource_manager_shared_resource" {
  source = "./modules/alicloud/r/alicloud_resource_manager_shared_resource"

  # resource_id - (required) is a type of string
  resource_id = null
  # resource_share_id - (required) is a type of string
  resource_share_id = null
  # resource_type - (required) is a type of string
  resource_type = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "resource_share_id" {
  description = "(required)"
  type        = string
}

variable "resource_type" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_shared_resource" "this" {
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # resource_share_id - (required) is a type of string
  resource_share_id = var.resource_share_id
  # resource_type - (required) is a type of string
  resource_type = var.resource_type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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
  value       = alicloud_resource_manager_shared_resource.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_resource_manager_shared_resource.this.status
}

output "this" {
  value = alicloud_resource_manager_shared_resource.this
}
```

[top](#index)