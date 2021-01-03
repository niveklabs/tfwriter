# fortios_wirelesscontroller_global

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontroller_global" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_global"

  # ap_log_server - (optional) is a type of string
  ap_log_server = null
  # ap_log_server_ip - (optional) is a type of string
  ap_log_server_ip = null
  # ap_log_server_port - (optional) is a type of number
  ap_log_server_port = null
  # control_message_offload - (optional) is a type of string
  control_message_offload = null
  # data_ethernet_ii - (optional) is a type of string
  data_ethernet_ii = null
  # discovery_mc_addr - (optional) is a type of string
  discovery_mc_addr = null
  # fiapp_eth_type - (optional) is a type of number
  fiapp_eth_type = null
  # image_download - (optional) is a type of string
  image_download = null
  # ipsec_base_ip - (optional) is a type of string
  ipsec_base_ip = null
  # link_aggregation - (optional) is a type of string
  link_aggregation = null
  # location - (optional) is a type of string
  location = null
  # max_clients - (optional) is a type of number
  max_clients = null
  # max_retransmit - (optional) is a type of number
  max_retransmit = null
  # mesh_eth_type - (optional) is a type of number
  mesh_eth_type = null
  # name - (optional) is a type of string
  name = null
  # rogue_scan_mac_adjacency - (optional) is a type of number
  rogue_scan_mac_adjacency = null
  # wtp_share - (optional) is a type of string
  wtp_share = null
}
```

[top](#index)

### Variables

```terraform
variable "ap_log_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_log_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_log_server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "control_message_offload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_ethernet_ii" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "discovery_mc_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fiapp_eth_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "image_download" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_base_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_aggregation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_clients" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_retransmit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mesh_eth_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rogue_scan_mac_adjacency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wtp_share" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_global" "this" {
  ap_log_server            = var.ap_log_server
  ap_log_server_ip         = var.ap_log_server_ip
  ap_log_server_port       = var.ap_log_server_port
  control_message_offload  = var.control_message_offload
  data_ethernet_ii         = var.data_ethernet_ii
  discovery_mc_addr        = var.discovery_mc_addr
  fiapp_eth_type           = var.fiapp_eth_type
  image_download           = var.image_download
  ipsec_base_ip            = var.ipsec_base_ip
  link_aggregation         = var.link_aggregation
  location                 = var.location
  max_clients              = var.max_clients
  max_retransmit           = var.max_retransmit
  mesh_eth_type            = var.mesh_eth_type
  name                     = var.name
  rogue_scan_mac_adjacency = var.rogue_scan_mac_adjacency
  wtp_share                = var.wtp_share
}
```

[top](#index)

### Outputs

```terraform
output "ap_log_server" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.ap_log_server
}

output "ap_log_server_ip" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.ap_log_server_ip
}

output "ap_log_server_port" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_global.this.ap_log_server_port
}

output "control_message_offload" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.control_message_offload
}

output "data_ethernet_ii" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.data_ethernet_ii
}

output "discovery_mc_addr" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.discovery_mc_addr
}

output "fiapp_eth_type" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_global.this.fiapp_eth_type
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.id
}

output "image_download" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.image_download
}

output "ipsec_base_ip" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.ipsec_base_ip
}

output "link_aggregation" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.link_aggregation
}

output "location" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.location
}

output "max_clients" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_global.this.max_clients
}

output "max_retransmit" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_global.this.max_retransmit
}

output "mesh_eth_type" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_global.this.mesh_eth_type
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.name
}

output "rogue_scan_mac_adjacency" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_global.this.rogue_scan_mac_adjacency
}

output "wtp_share" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_global.this.wtp_share
}

output "this" {
  value = fortios_wirelesscontroller_global.this
}
```

[top](#index)