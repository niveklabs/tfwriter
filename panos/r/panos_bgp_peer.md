# panos_bgp_peer

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
module "panos_bgp_peer" {
  source = "./modules/panos/r/panos_bgp_peer"

  # address_family_type - (optional) is a type of string
  address_family_type = null
  # allow_incoming_connections - (optional) is a type of bool
  allow_incoming_connections = null
  # allow_outgoing_connections - (optional) is a type of bool
  allow_outgoing_connections = null
  # auth_profile - (optional) is a type of string
  auth_profile = null
  # bfd_profile - (optional) is a type of string
  bfd_profile = null
  # bgp_peer_group - (required) is a type of string
  bgp_peer_group = null
  # enable - (optional) is a type of bool
  enable = null
  # enable_mp_bgp - (optional) is a type of bool
  enable_mp_bgp = null
  # enable_sender_side_loop_detection - (optional) is a type of bool
  enable_sender_side_loop_detection = null
  # hold_time - (optional) is a type of number
  hold_time = null
  # idle_hold_time - (optional) is a type of number
  idle_hold_time = null
  # incoming_connections_remote_port - (optional) is a type of number
  incoming_connections_remote_port = null
  # keep_alive_interval - (optional) is a type of number
  keep_alive_interval = null
  # local_address_interface - (required) is a type of string
  local_address_interface = null
  # local_address_ip - (optional) is a type of string
  local_address_ip = null
  # max_prefixes - (optional) is a type of string
  max_prefixes = null
  # min_route_advertisement_interval - (optional) is a type of number
  min_route_advertisement_interval = null
  # multi_hop - (optional) is a type of number
  multi_hop = null
  # name - (required) is a type of string
  name = null
  # open_delay_time - (optional) is a type of number
  open_delay_time = null
  # outgoing_connections_local_port - (optional) is a type of number
  outgoing_connections_local_port = null
  # peer_address_ip - (required) is a type of string
  peer_address_ip = null
  # peer_as - (optional) is a type of string
  peer_as = null
  # peering_type - (optional) is a type of string
  peering_type = null
  # reflector_client - (optional) is a type of string
  reflector_client = null
  # subsequent_address_family_multicast - (optional) is a type of bool
  subsequent_address_family_multicast = null
  # subsequent_address_family_unicast - (optional) is a type of bool
  subsequent_address_family_unicast = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "address_family_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_incoming_connections" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_outgoing_connections" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auth_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bfd_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_peer_group" {
  description = "(required)"
  type        = string
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_mp_bgp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_sender_side_loop_detection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hold_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_hold_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "incoming_connections_remote_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keep_alive_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_address_interface" {
  description = "(required)"
  type        = string
}

variable "local_address_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_prefixes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_route_advertisement_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "multi_hop" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "open_delay_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outgoing_connections_local_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "peer_address_ip" {
  description = "(required)"
  type        = string
}

variable "peer_as" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peering_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reflector_client" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subsequent_address_family_multicast" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "subsequent_address_family_unicast" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_bgp_peer" "this" {
  address_family_type                 = var.address_family_type
  allow_incoming_connections          = var.allow_incoming_connections
  allow_outgoing_connections          = var.allow_outgoing_connections
  auth_profile                        = var.auth_profile
  bfd_profile                         = var.bfd_profile
  bgp_peer_group                      = var.bgp_peer_group
  enable                              = var.enable
  enable_mp_bgp                       = var.enable_mp_bgp
  enable_sender_side_loop_detection   = var.enable_sender_side_loop_detection
  hold_time                           = var.hold_time
  idle_hold_time                      = var.idle_hold_time
  incoming_connections_remote_port    = var.incoming_connections_remote_port
  keep_alive_interval                 = var.keep_alive_interval
  local_address_interface             = var.local_address_interface
  local_address_ip                    = var.local_address_ip
  max_prefixes                        = var.max_prefixes
  min_route_advertisement_interval    = var.min_route_advertisement_interval
  multi_hop                           = var.multi_hop
  name                                = var.name
  open_delay_time                     = var.open_delay_time
  outgoing_connections_local_port     = var.outgoing_connections_local_port
  peer_address_ip                     = var.peer_address_ip
  peer_as                             = var.peer_as
  peering_type                        = var.peering_type
  reflector_client                    = var.reflector_client
  subsequent_address_family_multicast = var.subsequent_address_family_multicast
  subsequent_address_family_unicast   = var.subsequent_address_family_unicast
  virtual_router                      = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_bgp_peer.this.id
}

output "this" {
  value = panos_bgp_peer.this
}
```

[top](#index)