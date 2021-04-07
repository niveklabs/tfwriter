# tencentcloud_gaap_layer4_listener

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_gaap_layer4_listener" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_layer4_listener"

  # connect_timeout - (optional) is a type of number
  connect_timeout = null
  # health_check - (optional) is a type of bool
  health_check = null
  # interval - (optional) is a type of number
  interval = null
  # name - (required) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # proxy_id - (required) is a type of string
  proxy_id = null
  # realserver_type - (required) is a type of string
  realserver_type = null
  # scheduler - (optional) is a type of string
  scheduler = null

  realserver_bind_set = [{
    id     = null
    ip     = null
    port   = null
    weight = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connect_timeout" {
  description = "(optional) - Timeout of the health check response, should less than interval, default value is 2s. NOTES: Only supports listeners of `TCP` protocol and require less than `interval`."
  type        = number
  default     = null
}

variable "health_check" {
  description = "(optional) - Indicates whether health check is enable, default value is `false`. NOTES: Only supports listeners of `TCP` protocol."
  type        = bool
  default     = null
}

variable "interval" {
  description = "(optional) - Interval of the health check, default value is 5s. NOTES: Only supports listeners of `TCP` protocol."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the layer4 listener, the maximum length is 30."
  type        = string
}

variable "port" {
  description = "(required) - Port of the layer4 listener."
  type        = number
}

variable "protocol" {
  description = "(required) - Protocol of the layer4 listener. Valid value: `TCP` and `UDP`."
  type        = string
}

variable "proxy_id" {
  description = "(required) - ID of the GAAP proxy."
  type        = string
}

variable "realserver_type" {
  description = "(required) - Type of the realserver. Valid value: `IP` and `DOMAIN`. NOTES: when the `protocol` is specified as `TCP` and the `scheduler` is specified as `wrr`, the item can only be set to `IP`."
  type        = string
}

variable "scheduler" {
  description = "(optional) - Scheduling policy of the layer4 listener, default value is `rr`. Valid value: `rr`, `wrr` and `lc`."
  type        = string
  default     = null
}

variable "realserver_bind_set" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id     = string
      ip     = string
      port   = number
      weight = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_layer4_listener" "this" {
  # connect_timeout - (optional) is a type of number
  connect_timeout = var.connect_timeout
  # health_check - (optional) is a type of bool
  health_check = var.health_check
  # interval - (optional) is a type of number
  interval = var.interval
  # name - (required) is a type of string
  name = var.name
  # port - (required) is a type of number
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
  # proxy_id - (required) is a type of string
  proxy_id = var.proxy_id
  # realserver_type - (required) is a type of string
  realserver_type = var.realserver_type
  # scheduler - (optional) is a type of string
  scheduler = var.scheduler

  dynamic "realserver_bind_set" {
    for_each = var.realserver_bind_set
    content {
      # id - (required) is a type of string
      id = realserver_bind_set.value["id"]
      # ip - (required) is a type of string
      ip = realserver_bind_set.value["ip"]
      # port - (required) is a type of number
      port = realserver_bind_set.value["port"]
      # weight - (optional) is a type of number
      weight = realserver_bind_set.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_gaap_layer4_listener.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_layer4_listener.this.id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_gaap_layer4_listener.this.status
}

output "this" {
  value = tencentcloud_gaap_layer4_listener.this
}
```

[top](#index)