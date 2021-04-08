# vcd_edgegateway

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vcd/r/vcd_edgegateway"

  # configuration - (required) is a type of string
  configuration = null
  # description - (optional) is a type of string
  description = null
  # distributed_routing - (optional) is a type of bool
  distributed_routing = null
  # fips_mode_enabled - (optional) is a type of bool
  fips_mode_enabled = null
  # fw_default_rule_action - (optional) is a type of string
  fw_default_rule_action = null
  # fw_default_rule_logging_enabled - (optional) is a type of bool
  fw_default_rule_logging_enabled = null
  # fw_enabled - (optional) is a type of bool
  fw_enabled = null
  # ha_enabled - (optional) is a type of bool
  ha_enabled = null
  # lb_acceleration_enabled - (optional) is a type of bool
  lb_acceleration_enabled = null
  # lb_enabled - (optional) is a type of bool
  lb_enabled = null
  # lb_logging_enabled - (optional) is a type of bool
  lb_logging_enabled = null
  # lb_loglevel - (optional) is a type of string
  lb_loglevel = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # use_default_route_for_dns_relay - (optional) is a type of bool
  use_default_route_for_dns_relay = null
  # vdc - (optional) is a type of string
  vdc = null

  external_network = [{
    enable_rate_limit   = null
    incoming_rate_limit = null
    name                = null
    outgoing_rate_limit = null
    subnet = [{
      gateway    = null
      ip_address = null
      netmask    = null
      suballocate_pool = [{
        end_address   = null
        start_address = null
      }]
      use_for_default_route = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "configuration" {
  description = "(required) - Configuration of the vShield edge VM for this gateway. One of: compact, full (\"Large\"), full4 (\"Quad Large\"), x-large"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distributed_routing" {
  description = "(optional) - Enable distributed routing"
  type        = bool
  default     = null
}

variable "fips_mode_enabled" {
  description = "(optional) - Enable FIPS mode. FIPS mode turns on the cipher suites that comply with FIPS. (False by default)"
  type        = bool
  default     = null
}

variable "fw_default_rule_action" {
  description = "(optional) - 'accept' or 'deny'. Default 'deny'"
  type        = string
  default     = null
}

variable "fw_default_rule_logging_enabled" {
  description = "(optional) - Enable logging for default rule. Default 'false'"
  type        = bool
  default     = null
}

variable "fw_enabled" {
  description = "(optional) - Enable firewall. Default 'true'"
  type        = bool
  default     = null
}

variable "ha_enabled" {
  description = "(optional) - Enable high availability on this edge gateway"
  type        = bool
  default     = null
}

variable "lb_acceleration_enabled" {
  description = "(optional) - Enable load balancer acceleration. (Disabled by default)"
  type        = bool
  default     = null
}

variable "lb_enabled" {
  description = "(optional) - Enable load balancing. (Disabled by default)"
  type        = bool
  default     = null
}

variable "lb_logging_enabled" {
  description = "(optional) - Enable load balancer logging. (Disabled by default)"
  type        = bool
  default     = null
}

variable "lb_loglevel" {
  description = "(optional) - Log level. One of 'emergency', 'alert', 'critical', 'error', 'warning', 'notice', 'info', 'debug'. ('info' by default)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "use_default_route_for_dns_relay" {
  description = "(optional) - If true, default gateway will be used for the edge gateways' default routing and DNS forwarding.(False by default)"
  type        = bool
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "external_network" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      enable_rate_limit   = bool
      incoming_rate_limit = number
      name                = string
      outgoing_rate_limit = number
      subnet = set(object(
        {
          gateway    = string
          ip_address = string
          netmask    = string
          suballocate_pool = set(object(
            {
              end_address   = string
              start_address = string
            }
          ))
          use_for_default_route = bool
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_edgegateway" "this" {
  # configuration - (required) is a type of string
  configuration = var.configuration
  # description - (optional) is a type of string
  description = var.description
  # distributed_routing - (optional) is a type of bool
  distributed_routing = var.distributed_routing
  # fips_mode_enabled - (optional) is a type of bool
  fips_mode_enabled = var.fips_mode_enabled
  # fw_default_rule_action - (optional) is a type of string
  fw_default_rule_action = var.fw_default_rule_action
  # fw_default_rule_logging_enabled - (optional) is a type of bool
  fw_default_rule_logging_enabled = var.fw_default_rule_logging_enabled
  # fw_enabled - (optional) is a type of bool
  fw_enabled = var.fw_enabled
  # ha_enabled - (optional) is a type of bool
  ha_enabled = var.ha_enabled
  # lb_acceleration_enabled - (optional) is a type of bool
  lb_acceleration_enabled = var.lb_acceleration_enabled
  # lb_enabled - (optional) is a type of bool
  lb_enabled = var.lb_enabled
  # lb_logging_enabled - (optional) is a type of bool
  lb_logging_enabled = var.lb_logging_enabled
  # lb_loglevel - (optional) is a type of string
  lb_loglevel = var.lb_loglevel
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # use_default_route_for_dns_relay - (optional) is a type of bool
  use_default_route_for_dns_relay = var.use_default_route_for_dns_relay
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "external_network" {
    for_each = var.external_network
    content {
      # enable_rate_limit - (optional) is a type of bool
      enable_rate_limit = external_network.value["enable_rate_limit"]
      # incoming_rate_limit - (optional) is a type of number
      incoming_rate_limit = external_network.value["incoming_rate_limit"]
      # name - (required) is a type of string
      name = external_network.value["name"]
      # outgoing_rate_limit - (optional) is a type of number
      outgoing_rate_limit = external_network.value["outgoing_rate_limit"]

      dynamic "subnet" {
        for_each = external_network.value.subnet
        content {
          # gateway - (required) is a type of string
          gateway = subnet.value["gateway"]
          # ip_address - (optional) is a type of string
          ip_address = subnet.value["ip_address"]
          # netmask - (required) is a type of string
          netmask = subnet.value["netmask"]
          # use_for_default_route - (optional) is a type of bool
          use_for_default_route = subnet.value["use_for_default_route"]

          dynamic "suballocate_pool" {
            for_each = subnet.value.suballocate_pool
            content {
              # end_address - (required) is a type of string
              end_address = suballocate_pool.value["end_address"]
              # start_address - (required) is a type of string
              start_address = suballocate_pool.value["start_address"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_external_network_ip" {
  description = "returns a string"
  value       = vcd_edgegateway.this.default_external_network_ip
}

output "external_network_ips" {
  description = "returns a list of string"
  value       = vcd_edgegateway.this.external_network_ips
}

output "id" {
  description = "returns a string"
  value       = vcd_edgegateway.this.id
}

output "use_default_route_for_dns_relay" {
  description = "returns a bool"
  value       = vcd_edgegateway.this.use_default_route_for_dns_relay
}

output "this" {
  value = vcd_edgegateway.this
}
```

[top](#index)