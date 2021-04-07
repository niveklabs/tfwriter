# alicloud_ga_endpoint_group

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
module "alicloud_ga_endpoint_group" {
  source = "./modules/alicloud/r/alicloud_ga_endpoint_group"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # description - (optional) is a type of string
  description = null
  # endpoint_group_region - (required) is a type of string
  endpoint_group_region = null
  # endpoint_group_type - (optional) is a type of string
  endpoint_group_type = null
  # endpoint_request_protocol - (optional) is a type of string
  endpoint_request_protocol = null
  # health_check_interval_seconds - (optional) is a type of number
  health_check_interval_seconds = null
  # health_check_path - (optional) is a type of string
  health_check_path = null
  # health_check_port - (optional) is a type of number
  health_check_port = null
  # health_check_protocol - (optional) is a type of string
  health_check_protocol = null
  # listener_id - (required) is a type of string
  listener_id = null
  # name - (optional) is a type of string
  name = null
  # threshold_count - (optional) is a type of number
  threshold_count = null
  # traffic_percentage - (optional) is a type of number
  traffic_percentage = null

  endpoint_configurations = [{
    enable_clientip_preservation = null
    endpoint                     = null
    type                         = null
    weight                       = null
  }]

  port_overrides = [{
    endpoint_port = null
    listener_port = null
  }]

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
variable "accelerator_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_group_region" {
  description = "(required)"
  type        = string
}

variable "endpoint_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_request_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_interval_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listener_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "endpoint_configurations" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      enable_clientip_preservation = bool
      endpoint                     = string
      type                         = string
      weight                       = number
    }
  ))
}

variable "port_overrides" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      endpoint_port = number
      listener_port = number
    }
  ))
  default = []
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
resource "alicloud_ga_endpoint_group" "this" {
  # accelerator_id - (required) is a type of string
  accelerator_id = var.accelerator_id
  # description - (optional) is a type of string
  description = var.description
  # endpoint_group_region - (required) is a type of string
  endpoint_group_region = var.endpoint_group_region
  # endpoint_group_type - (optional) is a type of string
  endpoint_group_type = var.endpoint_group_type
  # endpoint_request_protocol - (optional) is a type of string
  endpoint_request_protocol = var.endpoint_request_protocol
  # health_check_interval_seconds - (optional) is a type of number
  health_check_interval_seconds = var.health_check_interval_seconds
  # health_check_path - (optional) is a type of string
  health_check_path = var.health_check_path
  # health_check_port - (optional) is a type of number
  health_check_port = var.health_check_port
  # health_check_protocol - (optional) is a type of string
  health_check_protocol = var.health_check_protocol
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # name - (optional) is a type of string
  name = var.name
  # threshold_count - (optional) is a type of number
  threshold_count = var.threshold_count
  # traffic_percentage - (optional) is a type of number
  traffic_percentage = var.traffic_percentage

  dynamic "endpoint_configurations" {
    for_each = var.endpoint_configurations
    content {
      # enable_clientip_preservation - (optional) is a type of bool
      enable_clientip_preservation = endpoint_configurations.value["enable_clientip_preservation"]
      # endpoint - (required) is a type of string
      endpoint = endpoint_configurations.value["endpoint"]
      # type - (required) is a type of string
      type = endpoint_configurations.value["type"]
      # weight - (required) is a type of number
      weight = endpoint_configurations.value["weight"]
    }
  }

  dynamic "port_overrides" {
    for_each = var.port_overrides
    content {
      # endpoint_port - (optional) is a type of number
      endpoint_port = port_overrides.value["endpoint_port"]
      # listener_port - (optional) is a type of number
      listener_port = port_overrides.value["listener_port"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = alicloud_ga_endpoint_group.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ga_endpoint_group.this.status
}

output "this" {
  value = alicloud_ga_endpoint_group.this
}
```

[top](#index)