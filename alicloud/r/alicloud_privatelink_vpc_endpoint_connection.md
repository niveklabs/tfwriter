# alicloud_privatelink_vpc_endpoint_connection

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
module "alicloud_privatelink_vpc_endpoint_connection" {
  source = "./modules/alicloud/r/alicloud_privatelink_vpc_endpoint_connection"

  # bandwidth - (optional) is a type of number
  bandwidth = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # endpoint_id - (required) is a type of string
  endpoint_id = null
  # service_id - (required) is a type of string
  service_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "endpoint_id" {
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
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_privatelink_vpc_endpoint_connection" "this" {
  bandwidth   = var.bandwidth
  dry_run     = var.dry_run
  endpoint_id = var.endpoint_id
  service_id  = var.service_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bandwidth" {
  description = "returns a number"
  value       = alicloud_privatelink_vpc_endpoint_connection.this.bandwidth
}

output "id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_connection.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_connection.this.status
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_connection.this
}
```

[top](#index)