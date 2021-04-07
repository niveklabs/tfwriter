# fortios_systemdhcp_server

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_systemdhcp_server" {
  source = "./modules/fortios/d/fortios_systemdhcp_server"

  # fosid - (required) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_systemdhcp_server" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "auto_configuration" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.auto_configuration
}

output "auto_managed_status" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.auto_managed_status
}

output "conflicted_ip_timeout" {
  description = "returns a number"
  value       = data.fortios_systemdhcp_server.this.conflicted_ip_timeout
}

output "ddns_auth" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_auth
}

output "ddns_key" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_key
  sensitive   = true
}

output "ddns_keyname" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_keyname
}

output "ddns_server_ip" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_server_ip
}

output "ddns_ttl" {
  description = "returns a number"
  value       = data.fortios_systemdhcp_server.this.ddns_ttl
}

output "ddns_update" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_update
}

output "ddns_update_override" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_update_override
}

output "ddns_zone" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ddns_zone
}

output "default_gateway" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.default_gateway
}

output "dhcp_settings_from_fortiipam" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.dhcp_settings_from_fortiipam
}

output "dns_server1" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.dns_server1
}

output "dns_server2" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.dns_server2
}

output "dns_server3" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.dns_server3
}

output "dns_server4" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.dns_server4
}

output "dns_service" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.dns_service
}

output "domain" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.domain
}

output "exclude_range" {
  description = "returns a list of object"
  value       = data.fortios_systemdhcp_server.this.exclude_range
}

output "filename" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.filename
}

output "forticlient_on_net_status" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.forticlient_on_net_status
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.interface
}

output "ip_mode" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ip_mode
}

output "ip_range" {
  description = "returns a list of object"
  value       = data.fortios_systemdhcp_server.this.ip_range
}

output "ipsec_lease_hold" {
  description = "returns a number"
  value       = data.fortios_systemdhcp_server.this.ipsec_lease_hold
}

output "lease_time" {
  description = "returns a number"
  value       = data.fortios_systemdhcp_server.this.lease_time
}

output "mac_acl_default_action" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.mac_acl_default_action
}

output "netmask" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.netmask
}

output "next_server" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.next_server
}

output "ntp_server1" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ntp_server1
}

output "ntp_server2" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ntp_server2
}

output "ntp_server3" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ntp_server3
}

output "ntp_service" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.ntp_service
}

output "options" {
  description = "returns a list of object"
  value       = data.fortios_systemdhcp_server.this.options
}

output "reserved_address" {
  description = "returns a list of object"
  value       = data.fortios_systemdhcp_server.this.reserved_address
}

output "server_type" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.server_type
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.status
}

output "tftp_server" {
  description = "returns a list of object"
  value       = data.fortios_systemdhcp_server.this.tftp_server
}

output "timezone" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.timezone
}

output "timezone_option" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.timezone_option
}

output "vci_match" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.vci_match
}

output "vci_string" {
  description = "returns a list of object"
  value       = data.fortios_systemdhcp_server.this.vci_string
}

output "wifi_ac1" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.wifi_ac1
}

output "wifi_ac2" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.wifi_ac2
}

output "wifi_ac3" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.wifi_ac3
}

output "wifi_ac_service" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.wifi_ac_service
}

output "wins_server1" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.wins_server1
}

output "wins_server2" {
  description = "returns a string"
  value       = data.fortios_systemdhcp_server.this.wins_server2
}

output "this" {
  value = fortios_systemdhcp_server.this
}
```

[top](#index)