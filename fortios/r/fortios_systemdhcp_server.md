# fortios_systemdhcp_server

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_systemdhcp_server" {
  source = "./modules/fortios/r/fortios_systemdhcp_server"

  # auto_configuration - (optional) is a type of string
  auto_configuration = null
  # auto_managed_status - (optional) is a type of string
  auto_managed_status = null
  # conflicted_ip_timeout - (optional) is a type of number
  conflicted_ip_timeout = null
  # ddns_auth - (optional) is a type of string
  ddns_auth = null
  # ddns_key - (optional) is a type of string
  ddns_key = null
  # ddns_keyname - (optional) is a type of string
  ddns_keyname = null
  # ddns_server_ip - (optional) is a type of string
  ddns_server_ip = null
  # ddns_ttl - (optional) is a type of number
  ddns_ttl = null
  # ddns_update - (optional) is a type of string
  ddns_update = null
  # ddns_update_override - (optional) is a type of string
  ddns_update_override = null
  # ddns_zone - (optional) is a type of string
  ddns_zone = null
  # default_gateway - (optional) is a type of string
  default_gateway = null
  # dhcp_settings_from_fortiipam - (optional) is a type of string
  dhcp_settings_from_fortiipam = null
  # dns_server1 - (optional) is a type of string
  dns_server1 = null
  # dns_server2 - (optional) is a type of string
  dns_server2 = null
  # dns_server3 - (optional) is a type of string
  dns_server3 = null
  # dns_server4 - (optional) is a type of string
  dns_server4 = null
  # dns_service - (optional) is a type of string
  dns_service = null
  # domain - (optional) is a type of string
  domain = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # filename - (optional) is a type of string
  filename = null
  # forticlient_on_net_status - (optional) is a type of string
  forticlient_on_net_status = null
  # fosid - (required) is a type of number
  fosid = null
  # interface - (required) is a type of string
  interface = null
  # ip_mode - (optional) is a type of string
  ip_mode = null
  # ipsec_lease_hold - (optional) is a type of number
  ipsec_lease_hold = null
  # lease_time - (optional) is a type of number
  lease_time = null
  # mac_acl_default_action - (optional) is a type of string
  mac_acl_default_action = null
  # netmask - (required) is a type of string
  netmask = null
  # next_server - (optional) is a type of string
  next_server = null
  # ntp_server1 - (optional) is a type of string
  ntp_server1 = null
  # ntp_server2 - (optional) is a type of string
  ntp_server2 = null
  # ntp_server3 - (optional) is a type of string
  ntp_server3 = null
  # ntp_service - (optional) is a type of string
  ntp_service = null
  # server_type - (optional) is a type of string
  server_type = null
  # status - (optional) is a type of string
  status = null
  # timezone - (optional) is a type of string
  timezone = null
  # timezone_option - (optional) is a type of string
  timezone_option = null
  # vci_match - (optional) is a type of string
  vci_match = null
  # wifi_ac1 - (optional) is a type of string
  wifi_ac1 = null
  # wifi_ac2 - (optional) is a type of string
  wifi_ac2 = null
  # wifi_ac3 - (optional) is a type of string
  wifi_ac3 = null
  # wifi_ac_service - (optional) is a type of string
  wifi_ac_service = null
  # wins_server1 - (optional) is a type of string
  wins_server1 = null
  # wins_server2 - (optional) is a type of string
  wins_server2 = null

  exclude_range = [{
    end_ip   = null
    id       = null
    start_ip = null
  }]

  ip_range = [{
    end_ip   = null
    id       = null
    start_ip = null
  }]

  options = [{
    code  = null
    id    = null
    ip    = null
    type  = null
    value = null
  }]

  reserved_address = [{
    action          = null
    circuit_id      = null
    circuit_id_type = null
    description     = null
    id              = null
    ip              = null
    mac             = null
    remote_id       = null
    remote_id_type  = null
    type            = null
  }]

  tftp_server = [{
    tftp_server = null
  }]

  vci_string = [{
    vci_string = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_managed_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conflicted_ip_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ddns_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_keyname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ddns_update" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_update_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_settings_from_fortiipam" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_on_net_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(required)"
  type        = number
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ip_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_lease_hold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lease_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac_acl_default_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netmask" {
  description = "(required)"
  type        = string
}

variable "next_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntp_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntp_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntp_server3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntp_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vci_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wifi_ac1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wifi_ac2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wifi_ac3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wifi_ac_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wins_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wins_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exclude_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end_ip   = string
      id       = number
      start_ip = string
    }
  ))
  default = []
}

variable "ip_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end_ip   = string
      id       = number
      start_ip = string
    }
  ))
  default = []
}

variable "options" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      code  = number
      id    = number
      ip    = string
      type  = string
      value = string
    }
  ))
  default = []
}

variable "reserved_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action          = string
      circuit_id      = string
      circuit_id_type = string
      description     = string
      id              = number
      ip              = string
      mac             = string
      remote_id       = string
      remote_id_type  = string
      type            = string
    }
  ))
  default = []
}

variable "tftp_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      tftp_server = string
    }
  ))
  default = []
}

variable "vci_string" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      vci_string = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemdhcp_server" "this" {
  auto_configuration           = var.auto_configuration
  auto_managed_status          = var.auto_managed_status
  conflicted_ip_timeout        = var.conflicted_ip_timeout
  ddns_auth                    = var.ddns_auth
  ddns_key                     = var.ddns_key
  ddns_keyname                 = var.ddns_keyname
  ddns_server_ip               = var.ddns_server_ip
  ddns_ttl                     = var.ddns_ttl
  ddns_update                  = var.ddns_update
  ddns_update_override         = var.ddns_update_override
  ddns_zone                    = var.ddns_zone
  default_gateway              = var.default_gateway
  dhcp_settings_from_fortiipam = var.dhcp_settings_from_fortiipam
  dns_server1                  = var.dns_server1
  dns_server2                  = var.dns_server2
  dns_server3                  = var.dns_server3
  dns_server4                  = var.dns_server4
  dns_service                  = var.dns_service
  domain                       = var.domain
  dynamic_sort_subtable        = var.dynamic_sort_subtable
  filename                     = var.filename
  forticlient_on_net_status    = var.forticlient_on_net_status
  fosid                        = var.fosid
  interface                    = var.interface
  ip_mode                      = var.ip_mode
  ipsec_lease_hold             = var.ipsec_lease_hold
  lease_time                   = var.lease_time
  mac_acl_default_action       = var.mac_acl_default_action
  netmask                      = var.netmask
  next_server                  = var.next_server
  ntp_server1                  = var.ntp_server1
  ntp_server2                  = var.ntp_server2
  ntp_server3                  = var.ntp_server3
  ntp_service                  = var.ntp_service
  server_type                  = var.server_type
  status                       = var.status
  timezone                     = var.timezone
  timezone_option              = var.timezone_option
  vci_match                    = var.vci_match
  wifi_ac1                     = var.wifi_ac1
  wifi_ac2                     = var.wifi_ac2
  wifi_ac3                     = var.wifi_ac3
  wifi_ac_service              = var.wifi_ac_service
  wins_server1                 = var.wins_server1
  wins_server2                 = var.wins_server2

  dynamic "exclude_range" {
    for_each = var.exclude_range
    content {
      end_ip   = exclude_range.value["end_ip"]
      id       = exclude_range.value["id"]
      start_ip = exclude_range.value["start_ip"]
    }
  }

  dynamic "ip_range" {
    for_each = var.ip_range
    content {
      end_ip   = ip_range.value["end_ip"]
      id       = ip_range.value["id"]
      start_ip = ip_range.value["start_ip"]
    }
  }

  dynamic "options" {
    for_each = var.options
    content {
      code  = options.value["code"]
      id    = options.value["id"]
      ip    = options.value["ip"]
      type  = options.value["type"]
      value = options.value["value"]
    }
  }

  dynamic "reserved_address" {
    for_each = var.reserved_address
    content {
      action          = reserved_address.value["action"]
      circuit_id      = reserved_address.value["circuit_id"]
      circuit_id_type = reserved_address.value["circuit_id_type"]
      description     = reserved_address.value["description"]
      id              = reserved_address.value["id"]
      ip              = reserved_address.value["ip"]
      mac             = reserved_address.value["mac"]
      remote_id       = reserved_address.value["remote_id"]
      remote_id_type  = reserved_address.value["remote_id_type"]
      type            = reserved_address.value["type"]
    }
  }

  dynamic "tftp_server" {
    for_each = var.tftp_server
    content {
      tftp_server = tftp_server.value["tftp_server"]
    }
  }

  dynamic "vci_string" {
    for_each = var.vci_string
    content {
      vci_string = vci_string.value["vci_string"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_configuration" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.auto_configuration
}

output "auto_managed_status" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.auto_managed_status
}

output "conflicted_ip_timeout" {
  description = "returns a number"
  value       = fortios_systemdhcp_server.this.conflicted_ip_timeout
}

output "ddns_auth" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_auth
}

output "ddns_key" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_key
  sensitive   = true
}

output "ddns_keyname" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_keyname
}

output "ddns_server_ip" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_server_ip
}

output "ddns_ttl" {
  description = "returns a number"
  value       = fortios_systemdhcp_server.this.ddns_ttl
}

output "ddns_update" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_update
}

output "ddns_update_override" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_update_override
}

output "ddns_zone" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ddns_zone
}

output "default_gateway" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.default_gateway
}

output "dhcp_settings_from_fortiipam" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.dhcp_settings_from_fortiipam
}

output "dns_server1" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.dns_server1
}

output "dns_server2" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.dns_server2
}

output "dns_server3" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.dns_server3
}

output "dns_server4" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.dns_server4
}

output "dns_service" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.dns_service
}

output "domain" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.domain
}

output "filename" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.filename
}

output "forticlient_on_net_status" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.forticlient_on_net_status
}

output "id" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.id
}

output "ip_mode" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ip_mode
}

output "ipsec_lease_hold" {
  description = "returns a number"
  value       = fortios_systemdhcp_server.this.ipsec_lease_hold
}

output "lease_time" {
  description = "returns a number"
  value       = fortios_systemdhcp_server.this.lease_time
}

output "mac_acl_default_action" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.mac_acl_default_action
}

output "next_server" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.next_server
}

output "ntp_server1" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ntp_server1
}

output "ntp_server2" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ntp_server2
}

output "ntp_server3" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ntp_server3
}

output "ntp_service" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.ntp_service
}

output "server_type" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.server_type
}

output "status" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.status
}

output "timezone" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.timezone
}

output "timezone_option" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.timezone_option
}

output "vci_match" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.vci_match
}

output "wifi_ac1" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.wifi_ac1
}

output "wifi_ac2" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.wifi_ac2
}

output "wifi_ac3" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.wifi_ac3
}

output "wifi_ac_service" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.wifi_ac_service
}

output "wins_server1" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.wins_server1
}

output "wins_server2" {
  description = "returns a string"
  value       = fortios_systemdhcp_server.this.wins_server2
}

output "this" {
  value = fortios_systemdhcp_server.this
}
```

[top](#index)