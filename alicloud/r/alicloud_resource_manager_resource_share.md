# alicloud_resource_manager_resource_share

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
module "alicloud_resource_manager_resource_share" {
  source = "./modules/alicloud/r/alicloud_resource_manager_resource_share"

  # resource_share_name - (required) is a type of string
  resource_share_name = null

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "resource_share_name" {
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
resource "alicloud_resource_manager_resource_share" "this" {
  resource_share_name = var.resource_share_name

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
  value       = alicloud_resource_manager_resource_share.this.id
}

output "resource_share_owner" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_share.this.resource_share_owner
}

output "status" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_share.this.status
}

output "this" {
  value = alicloud_resource_manager_resource_share.this
}
```

[top](#index)