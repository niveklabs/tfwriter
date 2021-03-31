# alicloud_vpc_flow_log

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
module "alicloud_vpc_flow_log" {
  source = "./modules/alicloud/r/alicloud_vpc_flow_log"

  # description - (optional) is a type of string
  description = null
  # flow_log_name - (optional) is a type of string
  flow_log_name = null
  # log_store_name - (required) is a type of string
  log_store_name = null
  # project_name - (required) is a type of string
  project_name = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # status - (optional) is a type of string
  status = null
  # traffic_type - (required) is a type of string
  traffic_type = null

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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_log_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_store_name" {
  description = "(required)"
  type        = string
}

variable "project_name" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "resource_type" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_type" {
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
resource "alicloud_vpc_flow_log" "this" {
  description    = var.description
  flow_log_name  = var.flow_log_name
  log_store_name = var.log_store_name
  project_name   = var.project_name
  resource_id    = var.resource_id
  resource_type  = var.resource_type
  status         = var.status
  traffic_type   = var.traffic_type

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
output "id" {
  description = "returns a string"
  value       = alicloud_vpc_flow_log.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_vpc_flow_log.this.status
}

output "this" {
  value = alicloud_vpc_flow_log.this
}
```

[top](#index)