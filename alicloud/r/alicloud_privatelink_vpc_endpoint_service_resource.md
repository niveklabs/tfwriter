# alicloud_privatelink_vpc_endpoint_service_resource

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
module "alicloud_privatelink_vpc_endpoint_service_resource" {
  source = "./modules/alicloud/r/alicloud_privatelink_vpc_endpoint_service_resource"

  # dry_run - (optional) is a type of bool
  dry_run = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # service_id - (required) is a type of string
  service_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "resource_type" {
  description = "(required)"
  type        = string
}

variable "service_id" {
  description = "(required)"
  type        = string
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
resource "alicloud_privatelink_vpc_endpoint_service_resource" "this" {
  dry_run       = var.dry_run
  resource_id   = var.resource_id
  resource_type = var.resource_type
  service_id    = var.service_id

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
output "id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_service_resource.this.id
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_service_resource.this
}
```

[top](#index)