# opc_compute_vpn_endpoint_v2

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_vpn_endpoint_v2" {
  source = "./modules/opc/r/opc_compute_vpn_endpoint_v2"

  # customer_vpn_gateway - (required) is a type of string
  customer_vpn_gateway = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ike_identifier - (optional) is a type of string
  ike_identifier = null
  # ip_network - (required) is a type of string
  ip_network = null
  # name - (required) is a type of string
  name = null
  # pre_shared_key - (required) is a type of string
  pre_shared_key = null
  # reachable_routes - (required) is a type of list of string
  reachable_routes = []
  # require_perfect_forward_secrecy - (optional) is a type of bool
  require_perfect_forward_secrecy = null
  # tags - (optional) is a type of list of string
  tags = []
  # vnic_sets - (required) is a type of list of string
  vnic_sets = []

  phase_one_settings = [{
    dh_group   = null
    encryption = null
    hash       = null
    lifetime   = null
  }]

  phase_two_settings = [{
    encryption = null
    hash       = null
    lifetime   = null
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
variable "customer_vpn_gateway" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ike_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_network" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pre_shared_key" {
  description = "(required)"
  type        = string
}

variable "reachable_routes" {
  description = "(required)"
  type        = list(string)
}

variable "require_perfect_forward_secrecy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "vnic_sets" {
  description = "(required)"
  type        = list(string)
}

variable "phase_one_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dh_group   = string
      encryption = string
      hash       = string
      lifetime   = number
    }
  ))
  default = []
}

variable "phase_two_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      encryption = string
      hash       = string
      lifetime   = number
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
resource "opc_compute_vpn_endpoint_v2" "this" {
  # customer_vpn_gateway - (required) is a type of string
  customer_vpn_gateway = var.customer_vpn_gateway
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # ike_identifier - (optional) is a type of string
  ike_identifier = var.ike_identifier
  # ip_network - (required) is a type of string
  ip_network = var.ip_network
  # name - (required) is a type of string
  name = var.name
  # pre_shared_key - (required) is a type of string
  pre_shared_key = var.pre_shared_key
  # reachable_routes - (required) is a type of list of string
  reachable_routes = var.reachable_routes
  # require_perfect_forward_secrecy - (optional) is a type of bool
  require_perfect_forward_secrecy = var.require_perfect_forward_secrecy
  # tags - (optional) is a type of list of string
  tags = var.tags
  # vnic_sets - (required) is a type of list of string
  vnic_sets = var.vnic_sets

  dynamic "phase_one_settings" {
    for_each = var.phase_one_settings
    content {
      # dh_group - (required) is a type of string
      dh_group = phase_one_settings.value["dh_group"]
      # encryption - (required) is a type of string
      encryption = phase_one_settings.value["encryption"]
      # hash - (required) is a type of string
      hash = phase_one_settings.value["hash"]
      # lifetime - (optional) is a type of number
      lifetime = phase_one_settings.value["lifetime"]
    }
  }

  dynamic "phase_two_settings" {
    for_each = var.phase_two_settings
    content {
      # encryption - (required) is a type of string
      encryption = phase_two_settings.value["encryption"]
      # hash - (required) is a type of string
      hash = phase_two_settings.value["hash"]
      # lifetime - (optional) is a type of number
      lifetime = phase_two_settings.value["lifetime"]
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
  value       = opc_compute_vpn_endpoint_v2.this.id
}

output "ike_identifier" {
  description = "returns a string"
  value       = opc_compute_vpn_endpoint_v2.this.ike_identifier
}

output "local_gateway_ip_address" {
  description = "returns a string"
  value       = opc_compute_vpn_endpoint_v2.this.local_gateway_ip_address
}

output "local_gateway_private_ip_address" {
  description = "returns a string"
  value       = opc_compute_vpn_endpoint_v2.this.local_gateway_private_ip_address
}

output "tunnel_status" {
  description = "returns a string"
  value       = opc_compute_vpn_endpoint_v2.this.tunnel_status
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_vpn_endpoint_v2.this.uri
}

output "this" {
  value = opc_compute_vpn_endpoint_v2.this
}
```

[top](#index)