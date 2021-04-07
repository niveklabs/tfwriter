# google_compute_vpn_tunnel

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_vpn_tunnel" {
  source = "./modules/google-beta/r/google_compute_vpn_tunnel"

  # description - (optional) is a type of string
  description = null
  # ike_version - (optional) is a type of number
  ike_version = null
  # labels - (optional) is a type of map of string
  labels = {}
  # local_traffic_selector - (optional) is a type of set of string
  local_traffic_selector = []
  # name - (required) is a type of string
  name = null
  # peer_external_gateway - (optional) is a type of string
  peer_external_gateway = null
  # peer_external_gateway_interface - (optional) is a type of number
  peer_external_gateway_interface = null
  # peer_gcp_gateway - (optional) is a type of string
  peer_gcp_gateway = null
  # peer_ip - (optional) is a type of string
  peer_ip = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # remote_traffic_selector - (optional) is a type of set of string
  remote_traffic_selector = []
  # router - (optional) is a type of string
  router = null
  # shared_secret - (required) is a type of string
  shared_secret = null
  # target_vpn_gateway - (optional) is a type of string
  target_vpn_gateway = null
  # vpn_gateway - (optional) is a type of string
  vpn_gateway = null
  # vpn_gateway_interface - (optional) is a type of number
  vpn_gateway_interface = null

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
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "ike_version" {
  description = "(optional) - IKE protocol version to use when establishing the VPN tunnel with\npeer VPN gateway.\nAcceptable IKE versions are 1 or 2. Default version is 2."
  type        = number
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this VpnTunnel."
  type        = map(string)
  default     = null
}

variable "local_traffic_selector" {
  description = "(optional) - Local traffic selector to use when establishing the VPN tunnel with\npeer VPN gateway. The value should be a CIDR formatted string,\nfor example '192.168.0.0/16'. The ranges should be disjoint.\nOnly IPv4 is supported."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. The name must be 1-63 characters long, and\ncomply with RFC1035. Specifically, the name must be 1-63\ncharacters long and match the regular expression\n'[a-z]([-a-z0-9]*[a-z0-9])?' which means the first character\nmust be a lowercase letter, and all following characters must\nbe a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "peer_external_gateway" {
  description = "(optional) - URL of the peer side external VPN gateway to which this VPN tunnel is connected."
  type        = string
  default     = null
}

variable "peer_external_gateway_interface" {
  description = "(optional) - The interface ID of the external VPN gateway to which this VPN tunnel is connected."
  type        = number
  default     = null
}

variable "peer_gcp_gateway" {
  description = "(optional) - URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected.\nIf provided, the VPN tunnel will automatically use the same vpn_gateway_interface\nID in the peer GCP VPN gateway.\nThis field must reference a 'google_compute_ha_vpn_gateway' resource."
  type        = string
  default     = null
}

variable "peer_ip" {
  description = "(optional) - IP address of the peer VPN gateway. Only IPv4 is supported."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region where the tunnel is located. If unset, is set to the region of 'target_vpn_gateway'."
  type        = string
  default     = null
}

variable "remote_traffic_selector" {
  description = "(optional) - Remote traffic selector to use when establishing the VPN tunnel with\npeer VPN gateway. The value should be a CIDR formatted string,\nfor example '192.168.0.0/16'. The ranges should be disjoint.\nOnly IPv4 is supported."
  type        = set(string)
  default     = null
}

variable "router" {
  description = "(optional) - URL of router resource to be used for dynamic routing."
  type        = string
  default     = null
}

variable "shared_secret" {
  description = "(required) - Shared secret used to set the secure session between the Cloud VPN\ngateway and the peer VPN gateway."
  type        = string
}

variable "target_vpn_gateway" {
  description = "(optional) - URL of the Target VPN gateway with which this VPN tunnel is\nassociated."
  type        = string
  default     = null
}

variable "vpn_gateway" {
  description = "(optional) - URL of the VPN gateway with which this VPN tunnel is associated.\nThis must be used if a High Availability VPN gateway resource is created.\nThis field must reference a 'google_compute_ha_vpn_gateway' resource."
  type        = string
  default     = null
}

variable "vpn_gateway_interface" {
  description = "(optional) - The interface ID of the VPN gateway with which this VPN tunnel is associated."
  type        = number
  default     = null
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
resource "google_compute_vpn_tunnel" "this" {
  # description - (optional) is a type of string
  description = var.description
  # ike_version - (optional) is a type of number
  ike_version = var.ike_version
  # labels - (optional) is a type of map of string
  labels = var.labels
  # local_traffic_selector - (optional) is a type of set of string
  local_traffic_selector = var.local_traffic_selector
  # name - (required) is a type of string
  name = var.name
  # peer_external_gateway - (optional) is a type of string
  peer_external_gateway = var.peer_external_gateway
  # peer_external_gateway_interface - (optional) is a type of number
  peer_external_gateway_interface = var.peer_external_gateway_interface
  # peer_gcp_gateway - (optional) is a type of string
  peer_gcp_gateway = var.peer_gcp_gateway
  # peer_ip - (optional) is a type of string
  peer_ip = var.peer_ip
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # remote_traffic_selector - (optional) is a type of set of string
  remote_traffic_selector = var.remote_traffic_selector
  # router - (optional) is a type of string
  router = var.router
  # shared_secret - (required) is a type of string
  shared_secret = var.shared_secret
  # target_vpn_gateway - (optional) is a type of string
  target_vpn_gateway = var.target_vpn_gateway
  # vpn_gateway - (optional) is a type of string
  vpn_gateway = var.vpn_gateway
  # vpn_gateway_interface - (optional) is a type of number
  vpn_gateway_interface = var.vpn_gateway_interface

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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.creation_timestamp
}

output "detailed_status" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.detailed_status
}

output "id" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.label_fingerprint
}

output "local_traffic_selector" {
  description = "returns a set of string"
  value       = google_compute_vpn_tunnel.this.local_traffic_selector
}

output "peer_ip" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.peer_ip
}

output "project" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.region
}

output "remote_traffic_selector" {
  description = "returns a set of string"
  value       = google_compute_vpn_tunnel.this.remote_traffic_selector
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.self_link
}

output "shared_secret_hash" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.shared_secret_hash
}

output "tunnel_id" {
  description = "returns a string"
  value       = google_compute_vpn_tunnel.this.tunnel_id
}

output "this" {
  value = google_compute_vpn_tunnel.this
}
```

[top](#index)