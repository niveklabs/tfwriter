# tencentcloud_gaap_http_rule

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
module "tencentcloud_gaap_http_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_http_rule"

  # connect_timeout - (optional) is a type of number
  connect_timeout = null
  # domain - (required) is a type of string
  domain = null
  # forward_host - (optional) is a type of string
  forward_host = null
  # health_check - (required) is a type of bool
  health_check = null
  # health_check_method - (optional) is a type of string
  health_check_method = null
  # health_check_path - (optional) is a type of string
  health_check_path = null
  # health_check_status_codes - (optional) is a type of set of number
  health_check_status_codes = []
  # interval - (optional) is a type of number
  interval = null
  # listener_id - (required) is a type of string
  listener_id = null
  # path - (required) is a type of string
  path = null
  # realserver_type - (required) is a type of string
  realserver_type = null
  # scheduler - (optional) is a type of string
  scheduler = null

  realservers = [{
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
  description = "(optional) - Timeout of the health check response, default value is 2s."
  type        = number
  default     = null
}

variable "domain" {
  description = "(required) - Forward domain of the forward rule."
  type        = string
}

variable "forward_host" {
  description = "(optional) - The default value of requested host which is forwarded to the realserver by the listener is `default`."
  type        = string
  default     = null
}

variable "health_check" {
  description = "(required) - Indicates whether health check is enable."
  type        = bool
}

variable "health_check_method" {
  description = "(optional) - Method of the health check. Valid value: `GET` and `HEAD`."
  type        = string
  default     = null
}

variable "health_check_path" {
  description = "(optional) - Path of health check. Maximum length is 80."
  type        = string
  default     = null
}

variable "health_check_status_codes" {
  description = "(optional) - Return code of confirmed normal. Valid value: `100`, `200`, `300`, `400` and `500`."
  type        = set(number)
  default     = null
}

variable "interval" {
  description = "(optional) - Interval of the health check, default value is 5s."
  type        = number
  default     = null
}

variable "listener_id" {
  description = "(required) - ID of the layer7 listener."
  type        = string
}

variable "path" {
  description = "(required) - Path of the forward rule. Maximum length is 80."
  type        = string
}

variable "realserver_type" {
  description = "(required) - Type of the realserver. Valid value: `IP` and `DOMAIN`."
  type        = string
}

variable "scheduler" {
  description = "(optional) - Scheduling policy of the forward rule, default value is `rr`. Valid value: `rr`, `wrr` and `lc`."
  type        = string
  default     = null
}

variable "realservers" {
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
resource "tencentcloud_gaap_http_rule" "this" {
  # connect_timeout - (optional) is a type of number
  connect_timeout = var.connect_timeout
  # domain - (required) is a type of string
  domain = var.domain
  # forward_host - (optional) is a type of string
  forward_host = var.forward_host
  # health_check - (required) is a type of bool
  health_check = var.health_check
  # health_check_method - (optional) is a type of string
  health_check_method = var.health_check_method
  # health_check_path - (optional) is a type of string
  health_check_path = var.health_check_path
  # health_check_status_codes - (optional) is a type of set of number
  health_check_status_codes = var.health_check_status_codes
  # interval - (optional) is a type of number
  interval = var.interval
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # path - (required) is a type of string
  path = var.path
  # realserver_type - (required) is a type of string
  realserver_type = var.realserver_type
  # scheduler - (optional) is a type of string
  scheduler = var.scheduler

  dynamic "realservers" {
    for_each = var.realservers
    content {
      # id - (required) is a type of string
      id = realservers.value["id"]
      # ip - (required) is a type of string
      ip = realservers.value["ip"]
      # port - (required) is a type of number
      port = realservers.value["port"]
      # weight - (optional) is a type of number
      weight = realservers.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "health_check_status_codes" {
  description = "returns a set of number"
  value       = tencentcloud_gaap_http_rule.this.health_check_status_codes
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_rule.this.id
}

output "this" {
  value = tencentcloud_gaap_http_rule.this
}
```

[top](#index)