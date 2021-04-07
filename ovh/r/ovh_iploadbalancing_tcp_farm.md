# ovh_iploadbalancing_tcp_farm

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_tcp_farm" {
  source = "./modules/ovh/r/ovh_iploadbalancing_tcp_farm"

  # balance - (optional) is a type of string
  balance = null
  # display_name - (optional) is a type of string
  display_name = null
  # port - (optional) is a type of number
  port = null
  # service_name - (required) is a type of string
  service_name = null
  # stickiness - (optional) is a type of string
  stickiness = null
  # vrack_network_id - (optional) is a type of number
  vrack_network_id = null
  # zone - (required) is a type of string
  zone = null

  probe = [{
    force_ssl = null
    interval  = null
    match     = null
    method    = null
    negate    = null
    pattern   = null
    port      = null
    type      = null
    url       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "balance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "stickiness" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrack_network_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "probe" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      force_ssl = bool
      interval  = number
      match     = string
      method    = string
      negate    = bool
      pattern   = string
      port      = number
      type      = string
      url       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_tcp_farm" "this" {
  # balance - (optional) is a type of string
  balance = var.balance
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # port - (optional) is a type of number
  port = var.port
  # service_name - (required) is a type of string
  service_name = var.service_name
  # stickiness - (optional) is a type of string
  stickiness = var.stickiness
  # vrack_network_id - (optional) is a type of number
  vrack_network_id = var.vrack_network_id
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "probe" {
    for_each = var.probe
    content {
      # force_ssl - (optional) is a type of bool
      force_ssl = probe.value["force_ssl"]
      # interval - (optional) is a type of number
      interval = probe.value["interval"]
      # match - (optional) is a type of string
      match = probe.value["match"]
      # method - (optional) is a type of string
      method = probe.value["method"]
      # negate - (optional) is a type of bool
      negate = probe.value["negate"]
      # pattern - (optional) is a type of string
      pattern = probe.value["pattern"]
      # port - (optional) is a type of number
      port = probe.value["port"]
      # type - (required) is a type of string
      type = probe.value["type"]
      # url - (optional) is a type of string
      url = probe.value["url"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_tcp_farm.this.id
}

output "this" {
  value = ovh_iploadbalancing_tcp_farm.this
}
```

[top](#index)