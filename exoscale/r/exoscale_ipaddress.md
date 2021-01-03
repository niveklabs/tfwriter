# exoscale_ipaddress

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_ipaddress" {
  source = "./modules/exoscale/r/exoscale_ipaddress"

  # description - (optional) is a type of string
  description = null
  # healthcheck_interval - (optional) is a type of number
  healthcheck_interval = null
  # healthcheck_mode - (optional) is a type of string
  healthcheck_mode = null
  # healthcheck_path - (optional) is a type of string
  healthcheck_path = null
  # healthcheck_port - (optional) is a type of number
  healthcheck_port = null
  # healthcheck_strikes_fail - (optional) is a type of number
  healthcheck_strikes_fail = null
  # healthcheck_strikes_ok - (optional) is a type of number
  healthcheck_strikes_ok = null
  # healthcheck_timeout - (optional) is a type of number
  healthcheck_timeout = null
  # healthcheck_tls_skip_verify - (optional) is a type of bool
  healthcheck_tls_skip_verify = null
  # healthcheck_tls_sni - (optional) is a type of string
  healthcheck_tls_sni = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone - (required) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
    read   = null
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

variable "healthcheck_interval" {
  description = "(optional) - Healthcheck probing interval in seconds"
  type        = number
  default     = null
}

variable "healthcheck_mode" {
  description = "(optional) - Healthcheck probing mode"
  type        = string
  default     = null
}

variable "healthcheck_path" {
  description = "(optional) - Healthcheck probe HTTP request path, must be specified in \"http\" mode"
  type        = string
  default     = null
}

variable "healthcheck_port" {
  description = "(optional) - Healthcheck service port to probe"
  type        = number
  default     = null
}

variable "healthcheck_strikes_fail" {
  description = "(optional) - Number of unsuccessful healthcheck probes before considering the target unhealthy"
  type        = number
  default     = null
}

variable "healthcheck_strikes_ok" {
  description = "(optional) - Number of successful healthcheck probes before considering the target healthy"
  type        = number
  default     = null
}

variable "healthcheck_timeout" {
  description = "(optional) - Time in seconds before considering a healthcheck probing failed"
  type        = number
  default     = null
}

variable "healthcheck_tls_skip_verify" {
  description = "(optional) - Healthcheck probe disable TLS verification"
  type        = bool
  default     = null
}

variable "healthcheck_tls_sni" {
  description = "(optional) - Healthcheck probe set server name for TLS SNI"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Map of tags (key: value)"
  type        = map(string)
  default     = null
}

variable "zone" {
  description = "(required) - Name of the zone"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_ipaddress" "this" {
  description                 = var.description
  healthcheck_interval        = var.healthcheck_interval
  healthcheck_mode            = var.healthcheck_mode
  healthcheck_path            = var.healthcheck_path
  healthcheck_port            = var.healthcheck_port
  healthcheck_strikes_fail    = var.healthcheck_strikes_fail
  healthcheck_strikes_ok      = var.healthcheck_strikes_ok
  healthcheck_timeout         = var.healthcheck_timeout
  healthcheck_tls_skip_verify = var.healthcheck_tls_skip_verify
  healthcheck_tls_sni         = var.healthcheck_tls_sni
  tags                        = var.tags
  zone                        = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
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
  value       = exoscale_ipaddress.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = exoscale_ipaddress.this.ip_address
}

output "tags" {
  description = "returns a map of string"
  value       = exoscale_ipaddress.this.tags
}

output "this" {
  value = exoscale_ipaddress.this
}
```

[top](#index)