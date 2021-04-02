# oci_core_ipsec_connection_tunnel

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_ipsec_connection_tunnel" {
  source = "./modules/oci/d/oci_core_ipsec_connection_tunnel"

  # ipsec_id - (required) is a type of string
  ipsec_id = null
  # tunnel_id - (required) is a type of string
  tunnel_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ipsec_id" {
  description = "(required)"
  type        = string
}

variable "tunnel_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_ipsec_connection_tunnel" "this" {
  ipsec_id  = var.ipsec_id
  tunnel_id = var.tunnel_id
}
```

[top](#index)

### Outputs

```terraform
output "bgp_session_info" {
  description = "returns a list of object"
  value       = data.oci_core_ipsec_connection_tunnel.this.bgp_session_info
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.compartment_id
}

output "cpe_ip" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.cpe_ip
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.display_name
}

output "encryption_domain_config" {
  description = "returns a list of object"
  value       = data.oci_core_ipsec_connection_tunnel.this.encryption_domain_config
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.id
}

output "ike_version" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.ike_version
}

output "routing" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.routing
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.state
}

output "status" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.status
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.time_created
}

output "time_status_updated" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.time_status_updated
}

output "vpn_ip" {
  description = "returns a string"
  value       = data.oci_core_ipsec_connection_tunnel.this.vpn_ip
}

output "this" {
  value = oci_core_ipsec_connection_tunnel.this
}
```

[top](#index)