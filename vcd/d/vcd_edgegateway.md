# vcd_edgegateway

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_edgegateway" {
  source = "./modules/vcd/d/vcd_edgegateway"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  filter = [{
    name_regex = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - name of the edge gateway. (Optional when 'filter' is used)"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name_regex = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vcd_edgegateway" "this" {
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "filter" {
    for_each = var.filter
    content {
      # name_regex - (optional) is a type of string
      name_regex = filter.value["name_regex"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "configuration" {
  description = "returns a string"
  value       = data.vcd_edgegateway.this.configuration
}

output "default_external_network_ip" {
  description = "returns a string"
  value       = data.vcd_edgegateway.this.default_external_network_ip
}

output "description" {
  description = "returns a string"
  value       = data.vcd_edgegateway.this.description
}

output "distributed_routing" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.distributed_routing
}

output "external_network" {
  description = "returns a set of object"
  value       = data.vcd_edgegateway.this.external_network
}

output "external_network_ips" {
  description = "returns a list of string"
  value       = data.vcd_edgegateway.this.external_network_ips
}

output "fips_mode_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.fips_mode_enabled
}

output "fw_default_rule_action" {
  description = "returns a string"
  value       = data.vcd_edgegateway.this.fw_default_rule_action
}

output "fw_default_rule_logging_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.fw_default_rule_logging_enabled
}

output "fw_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.fw_enabled
}

output "ha_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.ha_enabled
}

output "id" {
  description = "returns a string"
  value       = data.vcd_edgegateway.this.id
}

output "lb_acceleration_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.lb_acceleration_enabled
}

output "lb_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.lb_enabled
}

output "lb_logging_enabled" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.lb_logging_enabled
}

output "lb_loglevel" {
  description = "returns a string"
  value       = data.vcd_edgegateway.this.lb_loglevel
}

output "use_default_route_for_dns_relay" {
  description = "returns a bool"
  value       = data.vcd_edgegateway.this.use_default_route_for_dns_relay
}

output "this" {
  value = vcd_edgegateway.this
}
```

[top](#index)