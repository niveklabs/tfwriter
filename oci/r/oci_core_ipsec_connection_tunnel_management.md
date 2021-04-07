# oci_core_ipsec_connection_tunnel_management

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_ipsec_connection_tunnel_management" {
  source = "./modules/oci/r/oci_core_ipsec_connection_tunnel_management"

  # display_name - (optional) is a type of string
  display_name = null
  # ike_version - (optional) is a type of string
  ike_version = null
  # ipsec_id - (required) is a type of string
  ipsec_id = null
  # routing - (required) is a type of string
  routing = null
  # shared_secret - (optional) is a type of string
  shared_secret = null
  # tunnel_id - (required) is a type of string
  tunnel_id = null

  bgp_session_info = [{
    bgp_state             = null
    customer_bgp_asn      = null
    customer_interface_ip = null
    oracle_bgp_asn        = null
    oracle_interface_ip   = null
  }]

  encryption_domain_config = [{
    cpe_traffic_selector    = []
    oracle_traffic_selector = []
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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ike_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_id" {
  description = "(required)"
  type        = string
}

variable "routing" {
  description = "(required)"
  type        = string
}

variable "shared_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_id" {
  description = "(required)"
  type        = string
}

variable "bgp_session_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bgp_state             = string
      customer_bgp_asn      = string
      customer_interface_ip = string
      oracle_bgp_asn        = string
      oracle_interface_ip   = string
    }
  ))
  default = []
}

variable "encryption_domain_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cpe_traffic_selector    = list(string)
      oracle_traffic_selector = list(string)
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
resource "oci_core_ipsec_connection_tunnel_management" "this" {
  display_name  = var.display_name
  ike_version   = var.ike_version
  ipsec_id      = var.ipsec_id
  routing       = var.routing
  shared_secret = var.shared_secret
  tunnel_id     = var.tunnel_id

  dynamic "bgp_session_info" {
    for_each = var.bgp_session_info
    content {
      customer_bgp_asn      = bgp_session_info.value["customer_bgp_asn"]
      customer_interface_ip = bgp_session_info.value["customer_interface_ip"]
      oracle_interface_ip   = bgp_session_info.value["oracle_interface_ip"]
    }
  }

  dynamic "encryption_domain_config" {
    for_each = var.encryption_domain_config
    content {
      cpe_traffic_selector    = encryption_domain_config.value["cpe_traffic_selector"]
      oracle_traffic_selector = encryption_domain_config.value["oracle_traffic_selector"]
    }
  }

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.compartment_id
}

output "cpe_ip" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.cpe_ip
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.id
}

output "ike_version" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.ike_version
}

output "shared_secret" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.shared_secret
}

output "state" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.state
}

output "status" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.status
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.time_created
}

output "time_status_updated" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.time_status_updated
}

output "vpn_ip" {
  description = "returns a string"
  value       = oci_core_ipsec_connection_tunnel_management.this.vpn_ip
}

output "this" {
  value = oci_core_ipsec_connection_tunnel_management.this
}
```

[top](#index)