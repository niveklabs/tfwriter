# panos_ipsec_tunnel

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_ipsec_tunnel" {
  source = "./modules/panos/r/panos_ipsec_tunnel"

  # ak_ike_gateway - (optional) is a type of string
  ak_ike_gateway = null
  # ak_ipsec_crypto_profile - (optional) is a type of string
  ak_ipsec_crypto_profile = null
  # anti_replay - (optional) is a type of bool
  anti_replay = null
  # copy_flow_label - (optional) is a type of bool
  copy_flow_label = null
  # copy_tos - (optional) is a type of bool
  copy_tos = null
  # disabled - (optional) is a type of bool
  disabled = null
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = null
  # enable_tunnel_monitor - (optional) is a type of bool
  enable_tunnel_monitor = null
  # gps_certificate_profile - (optional) is a type of string
  gps_certificate_profile = null
  # gps_interface - (optional) is a type of string
  gps_interface = null
  # gps_interface_floating_ip_ipv4 - (optional) is a type of string
  gps_interface_floating_ip_ipv4 = null
  # gps_interface_floating_ip_ipv6 - (optional) is a type of string
  gps_interface_floating_ip_ipv6 = null
  # gps_interface_ip_ipv4 - (optional) is a type of string
  gps_interface_ip_ipv4 = null
  # gps_interface_ip_ipv6 - (optional) is a type of string
  gps_interface_ip_ipv6 = null
  # gps_local_certificate - (optional) is a type of string
  gps_local_certificate = null
  # gps_portal_address - (optional) is a type of string
  gps_portal_address = null
  # gps_prefer_ipv6 - (optional) is a type of bool
  gps_prefer_ipv6 = null
  # gps_publish_connected_routes - (optional) is a type of bool
  gps_publish_connected_routes = null
  # gps_publish_routes - (optional) is a type of list of string
  gps_publish_routes = []
  # mk_auth_key - (optional) is a type of string
  mk_auth_key = null
  # mk_auth_type - (optional) is a type of string
  mk_auth_type = null
  # mk_esp_encryption_key - (optional) is a type of string
  mk_esp_encryption_key = null
  # mk_esp_encryption_type - (optional) is a type of string
  mk_esp_encryption_type = null
  # mk_interface - (optional) is a type of string
  mk_interface = null
  # mk_local_address_floating_ip - (optional) is a type of string
  mk_local_address_floating_ip = null
  # mk_local_address_ip - (optional) is a type of string
  mk_local_address_ip = null
  # mk_local_spi - (optional) is a type of string
  mk_local_spi = null
  # mk_protocol - (optional) is a type of string
  mk_protocol = null
  # mk_remote_address - (optional) is a type of string
  mk_remote_address = null
  # mk_remote_spi - (optional) is a type of string
  mk_remote_spi = null
  # name - (required) is a type of string
  name = null
  # tunnel_interface - (required) is a type of string
  tunnel_interface = null
  # tunnel_monitor_destination_ip - (optional) is a type of string
  tunnel_monitor_destination_ip = null
  # tunnel_monitor_profile - (optional) is a type of string
  tunnel_monitor_profile = null
  # tunnel_monitor_proxy_id - (optional) is a type of string
  tunnel_monitor_proxy_id = null
  # tunnel_monitor_source_ip - (optional) is a type of string
  tunnel_monitor_source_ip = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "ak_ike_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ak_ipsec_crypto_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anti_replay" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "copy_flow_label" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "copy_tos" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_tunnel_monitor" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gps_certificate_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_interface_floating_ip_ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_interface_floating_ip_ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_interface_ip_ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_interface_ip_ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_local_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_portal_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gps_prefer_ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gps_publish_connected_routes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gps_publish_routes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "mk_auth_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_esp_encryption_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_esp_encryption_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_local_address_floating_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_local_address_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_local_spi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_remote_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mk_remote_spi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tunnel_interface" {
  description = "(required)"
  type        = string
}

variable "tunnel_monitor_destination_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_monitor_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_monitor_proxy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_monitor_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_ipsec_tunnel" "this" {
  ak_ike_gateway                 = var.ak_ike_gateway
  ak_ipsec_crypto_profile        = var.ak_ipsec_crypto_profile
  anti_replay                    = var.anti_replay
  copy_flow_label                = var.copy_flow_label
  copy_tos                       = var.copy_tos
  disabled                       = var.disabled
  enable_ipv6                    = var.enable_ipv6
  enable_tunnel_monitor          = var.enable_tunnel_monitor
  gps_certificate_profile        = var.gps_certificate_profile
  gps_interface                  = var.gps_interface
  gps_interface_floating_ip_ipv4 = var.gps_interface_floating_ip_ipv4
  gps_interface_floating_ip_ipv6 = var.gps_interface_floating_ip_ipv6
  gps_interface_ip_ipv4          = var.gps_interface_ip_ipv4
  gps_interface_ip_ipv6          = var.gps_interface_ip_ipv6
  gps_local_certificate          = var.gps_local_certificate
  gps_portal_address             = var.gps_portal_address
  gps_prefer_ipv6                = var.gps_prefer_ipv6
  gps_publish_connected_routes   = var.gps_publish_connected_routes
  gps_publish_routes             = var.gps_publish_routes
  mk_auth_key                    = var.mk_auth_key
  mk_auth_type                   = var.mk_auth_type
  mk_esp_encryption_key          = var.mk_esp_encryption_key
  mk_esp_encryption_type         = var.mk_esp_encryption_type
  mk_interface                   = var.mk_interface
  mk_local_address_floating_ip   = var.mk_local_address_floating_ip
  mk_local_address_ip            = var.mk_local_address_ip
  mk_local_spi                   = var.mk_local_spi
  mk_protocol                    = var.mk_protocol
  mk_remote_address              = var.mk_remote_address
  mk_remote_spi                  = var.mk_remote_spi
  name                           = var.name
  tunnel_interface               = var.tunnel_interface
  tunnel_monitor_destination_ip  = var.tunnel_monitor_destination_ip
  tunnel_monitor_profile         = var.tunnel_monitor_profile
  tunnel_monitor_proxy_id        = var.tunnel_monitor_proxy_id
  tunnel_monitor_source_ip       = var.tunnel_monitor_source_ip
  type                           = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ipsec_tunnel.this.id
}

output "mk_auth_key_enc" {
  description = "returns a string"
  value       = panos_ipsec_tunnel.this.mk_auth_key_enc
  sensitive   = true
}

output "mk_esp_encryption_key_enc" {
  description = "returns a string"
  value       = panos_ipsec_tunnel.this.mk_esp_encryption_key_enc
  sensitive   = true
}

output "this" {
  value = panos_ipsec_tunnel.this
}
```

[top](#index)