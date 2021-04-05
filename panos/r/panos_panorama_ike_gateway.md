# panos_panorama_ike_gateway

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
module "panos_panorama_ike_gateway" {
  source = "./modules/panos/r/panos_panorama_ike_gateway"

  # auth_type - (optional) is a type of string
  auth_type = null
  # cert_base_url - (optional) is a type of string
  cert_base_url = null
  # cert_enable_hash_and_url - (optional) is a type of bool
  cert_enable_hash_and_url = null
  # cert_enable_strict_validation - (optional) is a type of bool
  cert_enable_strict_validation = null
  # cert_permit_payload_mismatch - (optional) is a type of bool
  cert_permit_payload_mismatch = null
  # cert_profile - (optional) is a type of string
  cert_profile = null
  # cert_use_management_as_source - (optional) is a type of bool
  cert_use_management_as_source = null
  # dead_peer_detection_interval - (optional) is a type of number
  dead_peer_detection_interval = null
  # dead_peer_detection_retry - (optional) is a type of number
  dead_peer_detection_retry = null
  # disabled - (optional) is a type of bool
  disabled = null
  # enable_dead_peer_detection - (optional) is a type of bool
  enable_dead_peer_detection = null
  # enable_fragmentation - (optional) is a type of bool
  enable_fragmentation = null
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = null
  # enable_liveness_check - (optional) is a type of bool
  enable_liveness_check = null
  # enable_nat_traversal - (optional) is a type of bool
  enable_nat_traversal = null
  # enable_passive_mode - (optional) is a type of bool
  enable_passive_mode = null
  # ikev1_crypto_profile - (optional) is a type of string
  ikev1_crypto_profile = null
  # ikev1_exchange_mode - (optional) is a type of string
  ikev1_exchange_mode = null
  # ikev2_cookie_validation - (optional) is a type of bool
  ikev2_cookie_validation = null
  # ikev2_crypto_profile - (optional) is a type of string
  ikev2_crypto_profile = null
  # interface - (required) is a type of string
  interface = null
  # liveness_check_interval - (optional) is a type of number
  liveness_check_interval = null
  # local_cert - (optional) is a type of string
  local_cert = null
  # local_id_type - (optional) is a type of string
  local_id_type = null
  # local_id_value - (optional) is a type of string
  local_id_value = null
  # local_ip_address_type - (optional) is a type of string
  local_ip_address_type = null
  # local_ip_address_value - (optional) is a type of string
  local_ip_address_value = null
  # name - (required) is a type of string
  name = null
  # nat_traversal_enable_udp_checksum - (optional) is a type of bool
  nat_traversal_enable_udp_checksum = null
  # nat_traversal_keep_alive - (optional) is a type of number
  nat_traversal_keep_alive = null
  # peer_id_check - (optional) is a type of string
  peer_id_check = null
  # peer_id_type - (optional) is a type of string
  peer_id_type = null
  # peer_id_value - (optional) is a type of string
  peer_id_value = null
  # peer_ip_type - (optional) is a type of string
  peer_ip_type = null
  # peer_ip_value - (optional) is a type of string
  peer_ip_value = null
  # pre_shared_key - (optional) is a type of string
  pre_shared_key = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_base_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_enable_hash_and_url" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cert_enable_strict_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cert_permit_payload_mismatch" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cert_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_use_management_as_source" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dead_peer_detection_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dead_peer_detection_retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_dead_peer_detection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_fragmentation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_liveness_check" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_nat_traversal" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_passive_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ikev1_crypto_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ikev1_exchange_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ikev2_cookie_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ikev2_crypto_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "liveness_check_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_id_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_id_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_ip_address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_ip_address_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nat_traversal_enable_udp_checksum" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "nat_traversal_keep_alive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "peer_id_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_id_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_id_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_ip_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_ip_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pre_shared_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_ike_gateway" "this" {
  auth_type                         = var.auth_type
  cert_base_url                     = var.cert_base_url
  cert_enable_hash_and_url          = var.cert_enable_hash_and_url
  cert_enable_strict_validation     = var.cert_enable_strict_validation
  cert_permit_payload_mismatch      = var.cert_permit_payload_mismatch
  cert_profile                      = var.cert_profile
  cert_use_management_as_source     = var.cert_use_management_as_source
  dead_peer_detection_interval      = var.dead_peer_detection_interval
  dead_peer_detection_retry         = var.dead_peer_detection_retry
  disabled                          = var.disabled
  enable_dead_peer_detection        = var.enable_dead_peer_detection
  enable_fragmentation              = var.enable_fragmentation
  enable_ipv6                       = var.enable_ipv6
  enable_liveness_check             = var.enable_liveness_check
  enable_nat_traversal              = var.enable_nat_traversal
  enable_passive_mode               = var.enable_passive_mode
  ikev1_crypto_profile              = var.ikev1_crypto_profile
  ikev1_exchange_mode               = var.ikev1_exchange_mode
  ikev2_cookie_validation           = var.ikev2_cookie_validation
  ikev2_crypto_profile              = var.ikev2_crypto_profile
  interface                         = var.interface
  liveness_check_interval           = var.liveness_check_interval
  local_cert                        = var.local_cert
  local_id_type                     = var.local_id_type
  local_id_value                    = var.local_id_value
  local_ip_address_type             = var.local_ip_address_type
  local_ip_address_value            = var.local_ip_address_value
  name                              = var.name
  nat_traversal_enable_udp_checksum = var.nat_traversal_enable_udp_checksum
  nat_traversal_keep_alive          = var.nat_traversal_keep_alive
  peer_id_check                     = var.peer_id_check
  peer_id_type                      = var.peer_id_type
  peer_id_value                     = var.peer_id_value
  peer_ip_type                      = var.peer_ip_type
  peer_ip_value                     = var.peer_ip_value
  pre_shared_key                    = var.pre_shared_key
  template                          = var.template
  template_stack                    = var.template_stack
  version                           = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_ike_gateway.this.id
}

output "pre_shared_key_enc" {
  description = "returns a string"
  value       = panos_panorama_ike_gateway.this.pre_shared_key_enc
  sensitive   = true
}

output "this" {
  value = panos_panorama_ike_gateway.this
}
```

[top](#index)