# spotinst_health_check

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_health_check" {
  source = "./modules/spotinst/r/spotinst_health_check"

  # name - (optional) is a type of string
  name = null
  # proxy_address - (required) is a type of string
  proxy_address = null
  # proxy_port - (optional) is a type of number
  proxy_port = null
  # resource_id - (required) is a type of string
  resource_id = null

  check = [{
    end_point = null
    endpoint  = null
    healthy   = null
    interval  = null
    port      = null
    protocol  = null
    time_out  = null
    timeout   = null
    unhealthy = null
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

variable "proxy_address" {
  description = "(required)"
  type        = string
}

variable "proxy_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      end_point = string
      endpoint  = string
      healthy   = number
      interval  = number
      port      = number
      protocol  = string
      time_out  = number
      timeout   = number
      unhealthy = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_health_check" "this" {
  # name - (optional) is a type of string
  name = var.name
  # proxy_address - (required) is a type of string
  proxy_address = var.proxy_address
  # proxy_port - (optional) is a type of number
  proxy_port = var.proxy_port
  # resource_id - (required) is a type of string
  resource_id = var.resource_id

  dynamic "check" {
    for_each = var.check
    content {
      # end_point - (optional) is a type of string
      end_point = check.value["end_point"]
      # endpoint - (optional) is a type of string
      endpoint = check.value["endpoint"]
      # healthy - (required) is a type of number
      healthy = check.value["healthy"]
      # interval - (required) is a type of number
      interval = check.value["interval"]
      # port - (required) is a type of number
      port = check.value["port"]
      # protocol - (required) is a type of string
      protocol = check.value["protocol"]
      # time_out - (optional) is a type of number
      time_out = check.value["time_out"]
      # timeout - (optional) is a type of number
      timeout = check.value["timeout"]
      # unhealthy - (required) is a type of number
      unhealthy = check.value["unhealthy"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_health_check.this.id
}

output "this" {
  value = spotinst_health_check.this
}
```

[top](#index)