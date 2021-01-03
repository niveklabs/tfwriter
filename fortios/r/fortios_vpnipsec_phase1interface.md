# fortios_vpnipsec_phase1interface

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
module "fortios_vpnipsec_phase1interface" {
  source = "./modules/fortios/r/fortios_vpnipsec_phase1interface"

  # acct_verify - (optional) is a type of string
  acct_verify = null
  # add_gw_route - (optional) is a type of string
  add_gw_route = null
  # add_route - (optional) is a type of string
  add_route = null
  # assign_ip - (optional) is a type of string
  assign_ip = null
  # assign_ip_from - (optional) is a type of string
  assign_ip_from = null
  # authmethod - (optional) is a type of string
  authmethod = null
  # authmethod_remote - (optional) is a type of string
  authmethod_remote = null
  # authpasswd - (optional) is a type of string
  authpasswd = null
  # authusr - (optional) is a type of string
  authusr = null
  # authusrgrp - (optional) is a type of string
  authusrgrp = null
  # auto_discovery_forwarder - (optional) is a type of string
  auto_discovery_forwarder = null
  # auto_discovery_psk - (optional) is a type of string
  auto_discovery_psk = null
  # auto_discovery_receiver - (optional) is a type of string
  auto_discovery_receiver = null
  # auto_discovery_sender - (optional) is a type of string
  auto_discovery_sender = null
  # auto_negotiate - (optional) is a type of string
  auto_negotiate = null
  # banner - (optional) is a type of string
  banner = null
  # cert_id_validation - (optional) is a type of string
  cert_id_validation = null
  # childless_ike - (optional) is a type of string
  childless_ike = null
  # client_auto_negotiate - (optional) is a type of string
  client_auto_negotiate = null
  # client_keep_alive - (optional) is a type of string
  client_keep_alive = null
  # comments - (optional) is a type of string
  comments = null
  # default_gw - (optional) is a type of string
  default_gw = null
  # default_gw_priority - (optional) is a type of number
  default_gw_priority = null
  # dhgrp - (optional) is a type of string
  dhgrp = null
  # digital_signature_auth - (optional) is a type of string
  digital_signature_auth = null
  # distance - (optional) is a type of number
  distance = null
  # dns_mode - (optional) is a type of string
  dns_mode = null
  # domain - (optional) is a type of string
  domain = null
  # dpd - (optional) is a type of string
  dpd = null
  # dpd_retrycount - (optional) is a type of number
  dpd_retrycount = null
  # dpd_retryinterval - (optional) is a type of string
  dpd_retryinterval = null
  # eap - (optional) is a type of string
  eap = null
  # eap_identity - (optional) is a type of string
  eap_identity = null
  # encap_local_gw4 - (optional) is a type of string
  encap_local_gw4 = null
  # encap_local_gw6 - (optional) is a type of string
  encap_local_gw6 = null
  # encap_remote_gw4 - (optional) is a type of string
  encap_remote_gw4 = null
  # encap_remote_gw6 - (optional) is a type of string
  encap_remote_gw6 = null
  # encapsulation - (optional) is a type of string
  encapsulation = null
  # encapsulation_address - (optional) is a type of string
  encapsulation_address = null
  # enforce_unique_id - (optional) is a type of string
  enforce_unique_id = null
  # exchange_interface_ip - (optional) is a type of string
  exchange_interface_ip = null
  # exchange_ip_addr4 - (optional) is a type of string
  exchange_ip_addr4 = null
  # exchange_ip_addr6 - (optional) is a type of string
  exchange_ip_addr6 = null
  # forticlient_enforcement - (optional) is a type of string
  forticlient_enforcement = null
  # fragmentation - (optional) is a type of string
  fragmentation = null
  # fragmentation_mtu - (optional) is a type of number
  fragmentation_mtu = null
  # group_authentication - (optional) is a type of string
  group_authentication = null
  # group_authentication_secret - (optional) is a type of string
  group_authentication_secret = null
  # ha_sync_esp_seqno - (optional) is a type of string
  ha_sync_esp_seqno = null
  # idle_timeout - (optional) is a type of string
  idle_timeout = null
  # idle_timeoutinterval - (optional) is a type of number
  idle_timeoutinterval = null
  # ike_version - (optional) is a type of string
  ike_version = null
  # include_local_lan - (optional) is a type of string
  include_local_lan = null
  # interface - (required) is a type of string
  interface = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # ipv4_dns_server1 - (optional) is a type of string
  ipv4_dns_server1 = null
  # ipv4_dns_server2 - (optional) is a type of string
  ipv4_dns_server2 = null
  # ipv4_dns_server3 - (optional) is a type of string
  ipv4_dns_server3 = null
  # ipv4_end_ip - (optional) is a type of string
  ipv4_end_ip = null
  # ipv4_name - (optional) is a type of string
  ipv4_name = null
  # ipv4_netmask - (optional) is a type of string
  ipv4_netmask = null
  # ipv4_split_exclude - (optional) is a type of string
  ipv4_split_exclude = null
  # ipv4_split_include - (optional) is a type of string
  ipv4_split_include = null
  # ipv4_start_ip - (optional) is a type of string
  ipv4_start_ip = null
  # ipv4_wins_server1 - (optional) is a type of string
  ipv4_wins_server1 = null
  # ipv4_wins_server2 - (optional) is a type of string
  ipv4_wins_server2 = null
  # ipv6_dns_server1 - (optional) is a type of string
  ipv6_dns_server1 = null
  # ipv6_dns_server2 - (optional) is a type of string
  ipv6_dns_server2 = null
  # ipv6_dns_server3 - (optional) is a type of string
  ipv6_dns_server3 = null
  # ipv6_end_ip - (optional) is a type of string
  ipv6_end_ip = null
  # ipv6_name - (optional) is a type of string
  ipv6_name = null
  # ipv6_prefix - (optional) is a type of number
  ipv6_prefix = null
  # ipv6_split_exclude - (optional) is a type of string
  ipv6_split_exclude = null
  # ipv6_split_include - (optional) is a type of string
  ipv6_split_include = null
  # ipv6_start_ip - (optional) is a type of string
  ipv6_start_ip = null
  # keepalive - (optional) is a type of number
  keepalive = null
  # keylife - (optional) is a type of number
  keylife = null
  # local_gw - (optional) is a type of string
  local_gw = null
  # local_gw6 - (optional) is a type of string
  local_gw6 = null
  # localid - (optional) is a type of string
  localid = null
  # localid_type - (optional) is a type of string
  localid_type = null
  # mesh_selector_type - (optional) is a type of string
  mesh_selector_type = null
  # mode - (optional) is a type of string
  mode = null
  # mode_cfg - (optional) is a type of string
  mode_cfg = null
  # monitor - (optional) is a type of string
  monitor = null
  # monitor_hold_down_delay - (optional) is a type of number
  monitor_hold_down_delay = null
  # monitor_hold_down_time - (optional) is a type of string
  monitor_hold_down_time = null
  # monitor_hold_down_type - (optional) is a type of string
  monitor_hold_down_type = null
  # monitor_hold_down_weekday - (optional) is a type of string
  monitor_hold_down_weekday = null
  # name - (optional) is a type of string
  name = null
  # nattraversal - (optional) is a type of string
  nattraversal = null
  # negotiate_timeout - (optional) is a type of number
  negotiate_timeout = null
  # net_device - (optional) is a type of string
  net_device = null
  # passive_mode - (optional) is a type of string
  passive_mode = null
  # peer - (optional) is a type of string
  peer = null
  # peergrp - (optional) is a type of string
  peergrp = null
  # peerid - (optional) is a type of string
  peerid = null
  # peertype - (optional) is a type of string
  peertype = null
  # ppk - (optional) is a type of string
  ppk = null
  # ppk_identity - (optional) is a type of string
  ppk_identity = null
  # ppk_secret - (optional) is a type of string
  ppk_secret = null
  # priority - (optional) is a type of number
  priority = null
  # proposal - (required) is a type of string
  proposal = null
  # psksecret - (optional) is a type of string
  psksecret = null
  # psksecret_remote - (optional) is a type of string
  psksecret_remote = null
  # reauth - (optional) is a type of string
  reauth = null
  # rekey - (optional) is a type of string
  rekey = null
  # remote_gw - (optional) is a type of string
  remote_gw = null
  # remote_gw6 - (optional) is a type of string
  remote_gw6 = null
  # remotegw_ddns - (optional) is a type of string
  remotegw_ddns = null
  # rsa_signature_format - (optional) is a type of string
  rsa_signature_format = null
  # save_password - (optional) is a type of string
  save_password = null
  # send_cert_chain - (optional) is a type of string
  send_cert_chain = null
  # signature_hash_alg - (optional) is a type of string
  signature_hash_alg = null
  # split_include_service - (optional) is a type of string
  split_include_service = null
  # suite_b - (optional) is a type of string
  suite_b = null
  # tunnel_search - (optional) is a type of string
  tunnel_search = null
  # type - (optional) is a type of string
  type = null
  # unity_support - (optional) is a type of string
  unity_support = null
  # usrgrp - (optional) is a type of string
  usrgrp = null
  # vni - (optional) is a type of number
  vni = null
  # wizard_type - (optional) is a type of string
  wizard_type = null
  # xauthtype - (optional) is a type of string
  xauthtype = null

  backup_gateway = [{
    address = null
  }]

  certificate = [{
    name = null
  }]

  ipv4_exclude_range = [{
    end_ip   = null
    id       = null
    start_ip = null
  }]

  ipv6_exclude_range = [{
    end_ip   = null
    id       = null
    start_ip = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acct_verify" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "add_gw_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "add_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assign_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assign_ip_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authmethod" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authmethod_remote" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authpasswd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authusr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authusrgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_discovery_forwarder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_discovery_psk" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_discovery_receiver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_discovery_sender" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_negotiate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "banner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_id_validation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "childless_ike" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_auto_negotiate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_keep_alive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_gw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_gw_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dhgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "digital_signature_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dpd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dpd_retrycount" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dpd_retryinterval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap_identity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap_local_gw4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap_local_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap_remote_gw4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap_remote_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encapsulation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encapsulation_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enforce_unique_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exchange_interface_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exchange_ip_addr4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exchange_ip_addr6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_enforcement" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fragmentation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fragmentation_mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "group_authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_authentication_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_sync_esp_seqno" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idle_timeoutinterval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ike_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_local_lan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_dns_server3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_split_exclude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_split_include" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_wins_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_wins_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_dns_server3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_prefix" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_split_exclude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_split_include" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keepalive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keylife" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_gw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "localid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "localid_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mesh_selector_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode_cfg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_hold_down_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitor_hold_down_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_hold_down_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_hold_down_weekday" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nattraversal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "negotiate_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "net_device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passive_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peergrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peerid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peertype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppk" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppk_identity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppk_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proposal" {
  description = "(required)"
  type        = string
}

variable "psksecret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "psksecret_remote" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reauth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rekey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_gw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_gw6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remotegw_ddns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsa_signature_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "save_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "send_cert_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature_hash_alg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "split_include_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suite_b" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_search" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unity_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usrgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vni" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wizard_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "xauthtype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_gateway" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      address = string
    }
  ))
  default = []
}

variable "certificate" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "ipv4_exclude_range" {
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

variable "ipv6_exclude_range" {
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
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnipsec_phase1interface" "this" {
  acct_verify                 = var.acct_verify
  add_gw_route                = var.add_gw_route
  add_route                   = var.add_route
  assign_ip                   = var.assign_ip
  assign_ip_from              = var.assign_ip_from
  authmethod                  = var.authmethod
  authmethod_remote           = var.authmethod_remote
  authpasswd                  = var.authpasswd
  authusr                     = var.authusr
  authusrgrp                  = var.authusrgrp
  auto_discovery_forwarder    = var.auto_discovery_forwarder
  auto_discovery_psk          = var.auto_discovery_psk
  auto_discovery_receiver     = var.auto_discovery_receiver
  auto_discovery_sender       = var.auto_discovery_sender
  auto_negotiate              = var.auto_negotiate
  banner                      = var.banner
  cert_id_validation          = var.cert_id_validation
  childless_ike               = var.childless_ike
  client_auto_negotiate       = var.client_auto_negotiate
  client_keep_alive           = var.client_keep_alive
  comments                    = var.comments
  default_gw                  = var.default_gw
  default_gw_priority         = var.default_gw_priority
  dhgrp                       = var.dhgrp
  digital_signature_auth      = var.digital_signature_auth
  distance                    = var.distance
  dns_mode                    = var.dns_mode
  domain                      = var.domain
  dpd                         = var.dpd
  dpd_retrycount              = var.dpd_retrycount
  dpd_retryinterval           = var.dpd_retryinterval
  eap                         = var.eap
  eap_identity                = var.eap_identity
  encap_local_gw4             = var.encap_local_gw4
  encap_local_gw6             = var.encap_local_gw6
  encap_remote_gw4            = var.encap_remote_gw4
  encap_remote_gw6            = var.encap_remote_gw6
  encapsulation               = var.encapsulation
  encapsulation_address       = var.encapsulation_address
  enforce_unique_id           = var.enforce_unique_id
  exchange_interface_ip       = var.exchange_interface_ip
  exchange_ip_addr4           = var.exchange_ip_addr4
  exchange_ip_addr6           = var.exchange_ip_addr6
  forticlient_enforcement     = var.forticlient_enforcement
  fragmentation               = var.fragmentation
  fragmentation_mtu           = var.fragmentation_mtu
  group_authentication        = var.group_authentication
  group_authentication_secret = var.group_authentication_secret
  ha_sync_esp_seqno           = var.ha_sync_esp_seqno
  idle_timeout                = var.idle_timeout
  idle_timeoutinterval        = var.idle_timeoutinterval
  ike_version                 = var.ike_version
  include_local_lan           = var.include_local_lan
  interface                   = var.interface
  ip_version                  = var.ip_version
  ipv4_dns_server1            = var.ipv4_dns_server1
  ipv4_dns_server2            = var.ipv4_dns_server2
  ipv4_dns_server3            = var.ipv4_dns_server3
  ipv4_end_ip                 = var.ipv4_end_ip
  ipv4_name                   = var.ipv4_name
  ipv4_netmask                = var.ipv4_netmask
  ipv4_split_exclude          = var.ipv4_split_exclude
  ipv4_split_include          = var.ipv4_split_include
  ipv4_start_ip               = var.ipv4_start_ip
  ipv4_wins_server1           = var.ipv4_wins_server1
  ipv4_wins_server2           = var.ipv4_wins_server2
  ipv6_dns_server1            = var.ipv6_dns_server1
  ipv6_dns_server2            = var.ipv6_dns_server2
  ipv6_dns_server3            = var.ipv6_dns_server3
  ipv6_end_ip                 = var.ipv6_end_ip
  ipv6_name                   = var.ipv6_name
  ipv6_prefix                 = var.ipv6_prefix
  ipv6_split_exclude          = var.ipv6_split_exclude
  ipv6_split_include          = var.ipv6_split_include
  ipv6_start_ip               = var.ipv6_start_ip
  keepalive                   = var.keepalive
  keylife                     = var.keylife
  local_gw                    = var.local_gw
  local_gw6                   = var.local_gw6
  localid                     = var.localid
  localid_type                = var.localid_type
  mesh_selector_type          = var.mesh_selector_type
  mode                        = var.mode
  mode_cfg                    = var.mode_cfg
  monitor                     = var.monitor
  monitor_hold_down_delay     = var.monitor_hold_down_delay
  monitor_hold_down_time      = var.monitor_hold_down_time
  monitor_hold_down_type      = var.monitor_hold_down_type
  monitor_hold_down_weekday   = var.monitor_hold_down_weekday
  name                        = var.name
  nattraversal                = var.nattraversal
  negotiate_timeout           = var.negotiate_timeout
  net_device                  = var.net_device
  passive_mode                = var.passive_mode
  peer                        = var.peer
  peergrp                     = var.peergrp
  peerid                      = var.peerid
  peertype                    = var.peertype
  ppk                         = var.ppk
  ppk_identity                = var.ppk_identity
  ppk_secret                  = var.ppk_secret
  priority                    = var.priority
  proposal                    = var.proposal
  psksecret                   = var.psksecret
  psksecret_remote            = var.psksecret_remote
  reauth                      = var.reauth
  rekey                       = var.rekey
  remote_gw                   = var.remote_gw
  remote_gw6                  = var.remote_gw6
  remotegw_ddns               = var.remotegw_ddns
  rsa_signature_format        = var.rsa_signature_format
  save_password               = var.save_password
  send_cert_chain             = var.send_cert_chain
  signature_hash_alg          = var.signature_hash_alg
  split_include_service       = var.split_include_service
  suite_b                     = var.suite_b
  tunnel_search               = var.tunnel_search
  type                        = var.type
  unity_support               = var.unity_support
  usrgrp                      = var.usrgrp
  vni                         = var.vni
  wizard_type                 = var.wizard_type
  xauthtype                   = var.xauthtype

  dynamic "backup_gateway" {
    for_each = var.backup_gateway
    content {
      address = backup_gateway.value["address"]
    }
  }

  dynamic "certificate" {
    for_each = var.certificate
    content {
      name = certificate.value["name"]
    }
  }

  dynamic "ipv4_exclude_range" {
    for_each = var.ipv4_exclude_range
    content {
      end_ip   = ipv4_exclude_range.value["end_ip"]
      id       = ipv4_exclude_range.value["id"]
      start_ip = ipv4_exclude_range.value["start_ip"]
    }
  }

  dynamic "ipv6_exclude_range" {
    for_each = var.ipv6_exclude_range
    content {
      end_ip   = ipv6_exclude_range.value["end_ip"]
      id       = ipv6_exclude_range.value["id"]
      start_ip = ipv6_exclude_range.value["start_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "acct_verify" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.acct_verify
}

output "add_gw_route" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.add_gw_route
}

output "add_route" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.add_route
}

output "assign_ip" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.assign_ip
}

output "assign_ip_from" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.assign_ip_from
}

output "authmethod" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.authmethod
}

output "authmethod_remote" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.authmethod_remote
}

output "authusr" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.authusr
}

output "authusrgrp" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.authusrgrp
}

output "auto_discovery_forwarder" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.auto_discovery_forwarder
}

output "auto_discovery_psk" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.auto_discovery_psk
}

output "auto_discovery_receiver" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.auto_discovery_receiver
}

output "auto_discovery_sender" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.auto_discovery_sender
}

output "auto_negotiate" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.auto_negotiate
}

output "cert_id_validation" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.cert_id_validation
}

output "childless_ike" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.childless_ike
}

output "client_auto_negotiate" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.client_auto_negotiate
}

output "client_keep_alive" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.client_keep_alive
}

output "default_gw" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.default_gw
}

output "default_gw_priority" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.default_gw_priority
}

output "dhgrp" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.dhgrp
}

output "digital_signature_auth" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.digital_signature_auth
}

output "distance" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.distance
}

output "dns_mode" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.dns_mode
}

output "domain" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.domain
}

output "dpd" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.dpd
}

output "dpd_retrycount" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.dpd_retrycount
}

output "dpd_retryinterval" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.dpd_retryinterval
}

output "eap" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.eap
}

output "eap_identity" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.eap_identity
}

output "encap_local_gw4" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.encap_local_gw4
}

output "encap_local_gw6" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.encap_local_gw6
}

output "encap_remote_gw4" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.encap_remote_gw4
}

output "encap_remote_gw6" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.encap_remote_gw6
}

output "encapsulation" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.encapsulation
}

output "encapsulation_address" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.encapsulation_address
}

output "enforce_unique_id" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.enforce_unique_id
}

output "exchange_interface_ip" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.exchange_interface_ip
}

output "exchange_ip_addr4" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.exchange_ip_addr4
}

output "exchange_ip_addr6" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.exchange_ip_addr6
}

output "forticlient_enforcement" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.forticlient_enforcement
}

output "fragmentation" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.fragmentation
}

output "fragmentation_mtu" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.fragmentation_mtu
}

output "group_authentication" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.group_authentication
}

output "ha_sync_esp_seqno" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ha_sync_esp_seqno
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.id
}

output "idle_timeout" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.idle_timeout
}

output "idle_timeoutinterval" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.idle_timeoutinterval
}

output "ike_version" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ike_version
}

output "include_local_lan" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.include_local_lan
}

output "ip_version" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ip_version
}

output "ipv4_dns_server1" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_dns_server1
}

output "ipv4_dns_server2" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_dns_server2
}

output "ipv4_dns_server3" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_dns_server3
}

output "ipv4_end_ip" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_end_ip
}

output "ipv4_name" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_name
}

output "ipv4_netmask" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_netmask
}

output "ipv4_split_exclude" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_split_exclude
}

output "ipv4_split_include" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_split_include
}

output "ipv4_start_ip" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_start_ip
}

output "ipv4_wins_server1" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_wins_server1
}

output "ipv4_wins_server2" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv4_wins_server2
}

output "ipv6_dns_server1" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_dns_server1
}

output "ipv6_dns_server2" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_dns_server2
}

output "ipv6_dns_server3" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_dns_server3
}

output "ipv6_end_ip" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_end_ip
}

output "ipv6_name" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_name
}

output "ipv6_prefix" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_prefix
}

output "ipv6_split_exclude" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_split_exclude
}

output "ipv6_split_include" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_split_include
}

output "ipv6_start_ip" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ipv6_start_ip
}

output "keepalive" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.keepalive
}

output "keylife" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.keylife
}

output "local_gw" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.local_gw
}

output "local_gw6" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.local_gw6
}

output "localid" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.localid
}

output "localid_type" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.localid_type
}

output "mesh_selector_type" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.mesh_selector_type
}

output "mode" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.mode
}

output "mode_cfg" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.mode_cfg
}

output "monitor" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.monitor
}

output "monitor_hold_down_delay" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.monitor_hold_down_delay
}

output "monitor_hold_down_time" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.monitor_hold_down_time
}

output "monitor_hold_down_type" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.monitor_hold_down_type
}

output "monitor_hold_down_weekday" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.monitor_hold_down_weekday
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.name
}

output "nattraversal" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.nattraversal
}

output "negotiate_timeout" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.negotiate_timeout
}

output "net_device" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.net_device
}

output "passive_mode" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.passive_mode
}

output "peer" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.peer
}

output "peergrp" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.peergrp
}

output "peerid" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.peerid
}

output "peertype" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.peertype
}

output "ppk" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ppk
}

output "ppk_identity" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.ppk_identity
}

output "priority" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.priority
}

output "reauth" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.reauth
}

output "rekey" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.rekey
}

output "remote_gw" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.remote_gw
}

output "remote_gw6" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.remote_gw6
}

output "remotegw_ddns" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.remotegw_ddns
}

output "rsa_signature_format" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.rsa_signature_format
}

output "save_password" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.save_password
}

output "send_cert_chain" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.send_cert_chain
}

output "signature_hash_alg" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.signature_hash_alg
}

output "split_include_service" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.split_include_service
}

output "suite_b" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.suite_b
}

output "tunnel_search" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.tunnel_search
}

output "type" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.type
}

output "unity_support" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.unity_support
}

output "usrgrp" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.usrgrp
}

output "vni" {
  description = "returns a number"
  value       = fortios_vpnipsec_phase1interface.this.vni
}

output "wizard_type" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.wizard_type
}

output "xauthtype" {
  description = "returns a string"
  value       = fortios_vpnipsec_phase1interface.this.xauthtype
}

output "this" {
  value = fortios_vpnipsec_phase1interface.this
}
```

[top](#index)