# thunder_virtual_server

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_virtual_server" {
  source = "./modules/thunder/r/thunder_virtual_server"

  # acl_id - (optional) is a type of number
  acl_id = null
  # acl_id_shared - (optional) is a type of number
  acl_id_shared = null
  # acl_name - (optional) is a type of string
  acl_name = null
  # acl_name_shared - (optional) is a type of string
  acl_name_shared = null
  # arp_disable - (optional) is a type of number
  arp_disable = null
  # description - (optional) is a type of string
  description = null
  # disable_vip_adv - (optional) is a type of number
  disable_vip_adv = null
  # enable_disable_action - (optional) is a type of string
  enable_disable_action = null
  # ethernet - (optional) is a type of number
  ethernet = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # ha_dynamic - (optional) is a type of number
  ha_dynamic = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # ipv6_acl - (optional) is a type of string
  ipv6_acl = null
  # ipv6_acl_shared - (optional) is a type of string
  ipv6_acl_shared = null
  # name - (optional) is a type of string
  name = null
  # netmask - (optional) is a type of string
  netmask = null
  # redistribute_route_map - (optional) is a type of string
  redistribute_route_map = null
  # redistribution_flagged - (optional) is a type of number
  redistribution_flagged = null
  # shared_partition_policy_template - (optional) is a type of number
  shared_partition_policy_template = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
  # template_logging - (optional) is a type of string
  template_logging = null
  # template_policy - (optional) is a type of string
  template_policy = null
  # template_policy_acl - (optional) is a type of string
  template_policy_acl = null
  # template_policy_acl_shared - (optional) is a type of string
  template_policy_acl_shared = null
  # template_policy_address - (optional) is a type of string
  template_policy_address = null
  # template_policy_shared - (optional) is a type of string
  template_policy_shared = null
  # template_scaleout - (optional) is a type of string
  template_scaleout = null
  # template_virtual_server - (optional) is a type of string
  template_virtual_server = null
  # use_if_ip - (optional) is a type of number
  use_if_ip = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrid - (optional) is a type of number
  vrid = null

  migrate_vip = [{
    cancel_migration                = null
    finish_migration                = null
    target_data_cpu                 = null
    target_floating_ipv4            = null
    target_floating_template_policy = null
    uuid                            = null
  }]

  port_list = [{
    acl_id_list = [{
      acl_id                     = null
      acl_id_seq_num             = null
      acl_id_seq_num_shared      = null
      acl_id_src_nat_pool        = null
      acl_id_src_nat_pool_shared = null
      shared_partition_pool_id   = null
    }]
    acl_name_list = [{
      acl_name                     = null
      acl_name_seq_num             = null
      acl_name_seq_num_shared      = null
      acl_name_src_nat_pool        = null
      acl_name_src_nat_pool_shared = null
      shared_partition_pool_name   = null
    }]
    action = null
    aflex_scripts = [{
      aflex        = null
      aflex_shared = null
    }]
    alt_protocol1         = null
    alt_protocol2         = null
    alternate_port        = null
    alternate_port_number = null
    auth_cfg = [{
      aaa_policy = null
    }]
    auto                           = null
    clientip_sticky_nat            = null
    conn_limit                     = null
    def_selection_if_pref_failed   = null
    enable_playerid_check          = null
    eth_fwd                        = null
    eth_rev                        = null
    expand                         = null
    extended_stats                 = null
    force_routing_mode             = null
    gslb_enable                    = null
    ha_conn_mirror                 = null
    ip_map_list                    = null
    ipinip                         = null
    ipv6_acl                       = null
    l7_hardware_assist             = null
    message_switching              = null
    name                           = null
    no_auto_up_on_aflex            = null
    no_dest_nat                    = null
    no_logging                     = null
    on_syn                         = null
    optimization_level             = null
    persist_type                   = null
    pool                           = null
    pool_shared                    = null
    port_number                    = null
    port_translation               = null
    precedence                     = null
    protocol                       = null
    range                          = null
    rate                           = null
    redirect_to_https              = null
    req_fail                       = null
    reset                          = null
    reset_on_server_selection_fail = null
    rtp_sip_call_id_match          = null
    sampling_enable = [{
      counters1 = null
    }]
    scaleout_bucket_count                            = null
    scaleout_device_group                            = null
    secs                                             = null
    serv_sel_fail                                    = null
    service_group                                    = null
    shared_partition_cache_template                  = null
    shared_partition_client_ssl_template             = null
    shared_partition_connection_reuse_template       = null
    shared_partition_diameter_template               = null
    shared_partition_dns_template                    = null
    shared_partition_dynamic_service_template        = null
    shared_partition_external_service_template       = null
    shared_partition_http_policy_template            = null
    shared_partition_http_template                   = null
    shared_partition_persist_cookie_template         = null
    shared_partition_persist_destination_ip_template = null
    shared_partition_persist_source_ip_template      = null
    shared_partition_persist_ssl_sid_template        = null
    shared_partition_policy_template                 = null
    shared_partition_pool                            = null
    shared_partition_server_ssl_template             = null
    shared_partition_tcp                             = null
    shared_partition_tcp_proxy_template              = null
    shared_partition_udp                             = null
    shared_partition_virtual_port_template           = null
    skip_rev_hash                                    = null
    snat_on_vip                                      = null
    stats_data_action                                = null
    support_http2                                    = null
    syn_cookie                                       = null
    template_cache                                   = null
    template_cache_shared                            = null
    template_client_ssh                              = null
    template_client_ssl                              = null
    template_client_ssl_shared                       = null
    template_connection_reuse                        = null
    template_connection_reuse_shared                 = null
    template_dblb                                    = null
    template_diameter                                = null
    template_diameter_shared                         = null
    template_dns                                     = null
    template_dns_shared                              = null
    template_dynamic_service                         = null
    template_dynamic_service_shared                  = null
    template_external_service                        = null
    template_external_service_shared                 = null
    template_file_inspection                         = null
    template_fix                                     = null
    template_ftp                                     = null
    template_http                                    = null
    template_http_policy                             = null
    template_http_policy_shared                      = null
    template_http_shared                             = null
    template_imap_pop3                               = null
    template_persist_cookie                          = null
    template_persist_cookie_shared                   = null
    template_persist_destination_ip                  = null
    template_persist_destination_ip_shared           = null
    template_persist_source_ip                       = null
    template_persist_source_ip_shared                = null
    template_persist_ssl_sid                         = null
    template_persist_ssl_sid_shared                  = null
    template_policy                                  = null
    template_policy_shared                           = null
    template_reqmod_icap                             = null
    template_respmod_icap                            = null
    template_scaleout                                = null
    template_server_ssh                              = null
    template_server_ssl                              = null
    template_server_ssl_shared                       = null
    template_sip                                     = null
    template_smpp                                    = null
    template_smtp                                    = null
    template_ssli                                    = null
    template_tcp                                     = null
    template_tcp_proxy                               = null
    template_tcp_proxy_client                        = null
    template_tcp_proxy_server                        = null
    template_tcp_proxy_shared                        = null
    template_tcp_shared                              = null
    template_udp                                     = null
    template_udp_shared                              = null
    template_virtual_port                            = null
    template_virtual_port_shared                     = null
    trunk_fwd                                        = null
    trunk_rev                                        = null
    use_alternate_port                               = null
    use_cgnv6                                        = null
    use_default_if_no_server                         = null
    use_rcv_hop_for_resp                             = null
    user_tag                                         = null
    uuid                                             = null
    view                                             = null
    waf_template                                     = null
    when_down                                        = null
    when_down_protocol2                              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "acl_id_shared" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "acl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "acl_name_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_vip_adv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_disable_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ethernet" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_stats" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ha_dynamic" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_acl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_acl_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute_route_map" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribution_flagged" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_policy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stats_data_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_logging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy_acl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy_acl_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_scaleout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_virtual_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_if_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "migrate_vip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cancel_migration                = number
      finish_migration                = number
      target_data_cpu                 = number
      target_floating_ipv4            = string
      target_floating_template_policy = string
      uuid                            = string
    }
  ))
  default = []
}

variable "port_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      acl_id_list = list(object(
        {
          acl_id                     = number
          acl_id_seq_num             = number
          acl_id_seq_num_shared      = number
          acl_id_src_nat_pool        = string
          acl_id_src_nat_pool_shared = string
          shared_partition_pool_id   = number
        }
      ))
      acl_name_list = list(object(
        {
          acl_name                     = string
          acl_name_seq_num             = number
          acl_name_seq_num_shared      = number
          acl_name_src_nat_pool        = string
          acl_name_src_nat_pool_shared = string
          shared_partition_pool_name   = number
        }
      ))
      action = string
      aflex_scripts = list(object(
        {
          aflex        = string
          aflex_shared = string
        }
      ))
      alt_protocol1         = string
      alt_protocol2         = string
      alternate_port        = number
      alternate_port_number = number
      auth_cfg = list(object(
        {
          aaa_policy = string
        }
      ))
      auto                           = number
      clientip_sticky_nat            = number
      conn_limit                     = number
      def_selection_if_pref_failed   = string
      enable_playerid_check          = number
      eth_fwd                        = number
      eth_rev                        = number
      expand                         = number
      extended_stats                 = number
      force_routing_mode             = number
      gslb_enable                    = number
      ha_conn_mirror                 = number
      ip_map_list                    = string
      ipinip                         = number
      ipv6_acl                       = string
      l7_hardware_assist             = number
      message_switching              = number
      name                           = string
      no_auto_up_on_aflex            = number
      no_dest_nat                    = number
      no_logging                     = number
      on_syn                         = number
      optimization_level             = string
      persist_type                   = string
      pool                           = string
      pool_shared                    = string
      port_number                    = number
      port_translation               = number
      precedence                     = number
      protocol                       = string
      range                          = number
      rate                           = number
      redirect_to_https              = number
      req_fail                       = number
      reset                          = number
      reset_on_server_selection_fail = number
      rtp_sip_call_id_match          = number
      sampling_enable = list(object(
        {
          counters1 = string
        }
      ))
      scaleout_bucket_count                            = number
      scaleout_device_group                            = number
      secs                                             = number
      serv_sel_fail                                    = number
      service_group                                    = string
      shared_partition_cache_template                  = number
      shared_partition_client_ssl_template             = number
      shared_partition_connection_reuse_template       = number
      shared_partition_diameter_template               = number
      shared_partition_dns_template                    = number
      shared_partition_dynamic_service_template        = number
      shared_partition_external_service_template       = number
      shared_partition_http_policy_template            = number
      shared_partition_http_template                   = number
      shared_partition_persist_cookie_template         = number
      shared_partition_persist_destination_ip_template = number
      shared_partition_persist_source_ip_template      = number
      shared_partition_persist_ssl_sid_template        = number
      shared_partition_policy_template                 = number
      shared_partition_pool                            = number
      shared_partition_server_ssl_template             = number
      shared_partition_tcp                             = number
      shared_partition_tcp_proxy_template              = number
      shared_partition_udp                             = number
      shared_partition_virtual_port_template           = number
      skip_rev_hash                                    = number
      snat_on_vip                                      = number
      stats_data_action                                = string
      support_http2                                    = number
      syn_cookie                                       = number
      template_cache                                   = string
      template_cache_shared                            = string
      template_client_ssh                              = string
      template_client_ssl                              = string
      template_client_ssl_shared                       = string
      template_connection_reuse                        = string
      template_connection_reuse_shared                 = string
      template_dblb                                    = string
      template_diameter                                = string
      template_diameter_shared                         = string
      template_dns                                     = string
      template_dns_shared                              = string
      template_dynamic_service                         = string
      template_dynamic_service_shared                  = string
      template_external_service                        = string
      template_external_service_shared                 = string
      template_file_inspection                         = string
      template_fix                                     = string
      template_ftp                                     = string
      template_http                                    = string
      template_http_policy                             = string
      template_http_policy_shared                      = string
      template_http_shared                             = string
      template_imap_pop3                               = string
      template_persist_cookie                          = string
      template_persist_cookie_shared                   = string
      template_persist_destination_ip                  = string
      template_persist_destination_ip_shared           = string
      template_persist_source_ip                       = string
      template_persist_source_ip_shared                = string
      template_persist_ssl_sid                         = string
      template_persist_ssl_sid_shared                  = string
      template_policy                                  = string
      template_policy_shared                           = string
      template_reqmod_icap                             = string
      template_respmod_icap                            = string
      template_scaleout                                = string
      template_server_ssh                              = string
      template_server_ssl                              = string
      template_server_ssl_shared                       = string
      template_sip                                     = string
      template_smpp                                    = string
      template_smtp                                    = string
      template_ssli                                    = string
      template_tcp                                     = string
      template_tcp_proxy                               = string
      template_tcp_proxy_client                        = string
      template_tcp_proxy_server                        = string
      template_tcp_proxy_shared                        = string
      template_tcp_shared                              = string
      template_udp                                     = string
      template_udp_shared                              = string
      template_virtual_port                            = string
      template_virtual_port_shared                     = string
      trunk_fwd                                        = number
      trunk_rev                                        = number
      use_alternate_port                               = number
      use_cgnv6                                        = number
      use_default_if_no_server                         = number
      use_rcv_hop_for_resp                             = number
      user_tag                                         = string
      uuid                                             = string
      view                                             = number
      waf_template                                     = string
      when_down                                        = number
      when_down_protocol2                              = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_virtual_server" "this" {
  # acl_id - (optional) is a type of number
  acl_id = var.acl_id
  # acl_id_shared - (optional) is a type of number
  acl_id_shared = var.acl_id_shared
  # acl_name - (optional) is a type of string
  acl_name = var.acl_name
  # acl_name_shared - (optional) is a type of string
  acl_name_shared = var.acl_name_shared
  # arp_disable - (optional) is a type of number
  arp_disable = var.arp_disable
  # description - (optional) is a type of string
  description = var.description
  # disable_vip_adv - (optional) is a type of number
  disable_vip_adv = var.disable_vip_adv
  # enable_disable_action - (optional) is a type of string
  enable_disable_action = var.enable_disable_action
  # ethernet - (optional) is a type of number
  ethernet = var.ethernet
  # extended_stats - (optional) is a type of number
  extended_stats = var.extended_stats
  # ha_dynamic - (optional) is a type of number
  ha_dynamic = var.ha_dynamic
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # ipv6_acl - (optional) is a type of string
  ipv6_acl = var.ipv6_acl
  # ipv6_acl_shared - (optional) is a type of string
  ipv6_acl_shared = var.ipv6_acl_shared
  # name - (optional) is a type of string
  name = var.name
  # netmask - (optional) is a type of string
  netmask = var.netmask
  # redistribute_route_map - (optional) is a type of string
  redistribute_route_map = var.redistribute_route_map
  # redistribution_flagged - (optional) is a type of number
  redistribution_flagged = var.redistribution_flagged
  # shared_partition_policy_template - (optional) is a type of number
  shared_partition_policy_template = var.shared_partition_policy_template
  # stats_data_action - (optional) is a type of string
  stats_data_action = var.stats_data_action
  # template_logging - (optional) is a type of string
  template_logging = var.template_logging
  # template_policy - (optional) is a type of string
  template_policy = var.template_policy
  # template_policy_acl - (optional) is a type of string
  template_policy_acl = var.template_policy_acl
  # template_policy_acl_shared - (optional) is a type of string
  template_policy_acl_shared = var.template_policy_acl_shared
  # template_policy_address - (optional) is a type of string
  template_policy_address = var.template_policy_address
  # template_policy_shared - (optional) is a type of string
  template_policy_shared = var.template_policy_shared
  # template_scaleout - (optional) is a type of string
  template_scaleout = var.template_scaleout
  # template_virtual_server - (optional) is a type of string
  template_virtual_server = var.template_virtual_server
  # use_if_ip - (optional) is a type of number
  use_if_ip = var.use_if_ip
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vrid - (optional) is a type of number
  vrid = var.vrid

  dynamic "migrate_vip" {
    for_each = var.migrate_vip
    content {
      # cancel_migration - (optional) is a type of number
      cancel_migration = migrate_vip.value["cancel_migration"]
      # finish_migration - (optional) is a type of number
      finish_migration = migrate_vip.value["finish_migration"]
      # target_data_cpu - (optional) is a type of number
      target_data_cpu = migrate_vip.value["target_data_cpu"]
      # target_floating_ipv4 - (optional) is a type of string
      target_floating_ipv4 = migrate_vip.value["target_floating_ipv4"]
      # target_floating_template_policy - (optional) is a type of string
      target_floating_template_policy = migrate_vip.value["target_floating_template_policy"]
      # uuid - (optional) is a type of string
      uuid = migrate_vip.value["uuid"]
    }
  }

  dynamic "port_list" {
    for_each = var.port_list
    content {
      # action - (optional) is a type of string
      action = port_list.value["action"]
      # alt_protocol1 - (optional) is a type of string
      alt_protocol1 = port_list.value["alt_protocol1"]
      # alt_protocol2 - (optional) is a type of string
      alt_protocol2 = port_list.value["alt_protocol2"]
      # alternate_port - (optional) is a type of number
      alternate_port = port_list.value["alternate_port"]
      # alternate_port_number - (optional) is a type of number
      alternate_port_number = port_list.value["alternate_port_number"]
      # auto - (optional) is a type of number
      auto = port_list.value["auto"]
      # clientip_sticky_nat - (optional) is a type of number
      clientip_sticky_nat = port_list.value["clientip_sticky_nat"]
      # conn_limit - (optional) is a type of number
      conn_limit = port_list.value["conn_limit"]
      # def_selection_if_pref_failed - (optional) is a type of string
      def_selection_if_pref_failed = port_list.value["def_selection_if_pref_failed"]
      # enable_playerid_check - (optional) is a type of number
      enable_playerid_check = port_list.value["enable_playerid_check"]
      # eth_fwd - (optional) is a type of number
      eth_fwd = port_list.value["eth_fwd"]
      # eth_rev - (optional) is a type of number
      eth_rev = port_list.value["eth_rev"]
      # expand - (optional) is a type of number
      expand = port_list.value["expand"]
      # extended_stats - (optional) is a type of number
      extended_stats = port_list.value["extended_stats"]
      # force_routing_mode - (optional) is a type of number
      force_routing_mode = port_list.value["force_routing_mode"]
      # gslb_enable - (optional) is a type of number
      gslb_enable = port_list.value["gslb_enable"]
      # ha_conn_mirror - (optional) is a type of number
      ha_conn_mirror = port_list.value["ha_conn_mirror"]
      # ip_map_list - (optional) is a type of string
      ip_map_list = port_list.value["ip_map_list"]
      # ipinip - (optional) is a type of number
      ipinip = port_list.value["ipinip"]
      # ipv6_acl - (optional) is a type of string
      ipv6_acl = port_list.value["ipv6_acl"]
      # l7_hardware_assist - (optional) is a type of number
      l7_hardware_assist = port_list.value["l7_hardware_assist"]
      # message_switching - (optional) is a type of number
      message_switching = port_list.value["message_switching"]
      # name - (optional) is a type of string
      name = port_list.value["name"]
      # no_auto_up_on_aflex - (optional) is a type of number
      no_auto_up_on_aflex = port_list.value["no_auto_up_on_aflex"]
      # no_dest_nat - (optional) is a type of number
      no_dest_nat = port_list.value["no_dest_nat"]
      # no_logging - (optional) is a type of number
      no_logging = port_list.value["no_logging"]
      # on_syn - (optional) is a type of number
      on_syn = port_list.value["on_syn"]
      # optimization_level - (optional) is a type of string
      optimization_level = port_list.value["optimization_level"]
      # persist_type - (optional) is a type of string
      persist_type = port_list.value["persist_type"]
      # pool - (optional) is a type of string
      pool = port_list.value["pool"]
      # pool_shared - (optional) is a type of string
      pool_shared = port_list.value["pool_shared"]
      # port_number - (optional) is a type of number
      port_number = port_list.value["port_number"]
      # port_translation - (optional) is a type of number
      port_translation = port_list.value["port_translation"]
      # precedence - (optional) is a type of number
      precedence = port_list.value["precedence"]
      # protocol - (optional) is a type of string
      protocol = port_list.value["protocol"]
      # range - (optional) is a type of number
      range = port_list.value["range"]
      # rate - (optional) is a type of number
      rate = port_list.value["rate"]
      # redirect_to_https - (optional) is a type of number
      redirect_to_https = port_list.value["redirect_to_https"]
      # req_fail - (optional) is a type of number
      req_fail = port_list.value["req_fail"]
      # reset - (optional) is a type of number
      reset = port_list.value["reset"]
      # reset_on_server_selection_fail - (optional) is a type of number
      reset_on_server_selection_fail = port_list.value["reset_on_server_selection_fail"]
      # rtp_sip_call_id_match - (optional) is a type of number
      rtp_sip_call_id_match = port_list.value["rtp_sip_call_id_match"]
      # scaleout_bucket_count - (optional) is a type of number
      scaleout_bucket_count = port_list.value["scaleout_bucket_count"]
      # scaleout_device_group - (optional) is a type of number
      scaleout_device_group = port_list.value["scaleout_device_group"]
      # secs - (optional) is a type of number
      secs = port_list.value["secs"]
      # serv_sel_fail - (optional) is a type of number
      serv_sel_fail = port_list.value["serv_sel_fail"]
      # service_group - (optional) is a type of string
      service_group = port_list.value["service_group"]
      # shared_partition_cache_template - (optional) is a type of number
      shared_partition_cache_template = port_list.value["shared_partition_cache_template"]
      # shared_partition_client_ssl_template - (optional) is a type of number
      shared_partition_client_ssl_template = port_list.value["shared_partition_client_ssl_template"]
      # shared_partition_connection_reuse_template - (optional) is a type of number
      shared_partition_connection_reuse_template = port_list.value["shared_partition_connection_reuse_template"]
      # shared_partition_diameter_template - (optional) is a type of number
      shared_partition_diameter_template = port_list.value["shared_partition_diameter_template"]
      # shared_partition_dns_template - (optional) is a type of number
      shared_partition_dns_template = port_list.value["shared_partition_dns_template"]
      # shared_partition_dynamic_service_template - (optional) is a type of number
      shared_partition_dynamic_service_template = port_list.value["shared_partition_dynamic_service_template"]
      # shared_partition_external_service_template - (optional) is a type of number
      shared_partition_external_service_template = port_list.value["shared_partition_external_service_template"]
      # shared_partition_http_policy_template - (optional) is a type of number
      shared_partition_http_policy_template = port_list.value["shared_partition_http_policy_template"]
      # shared_partition_http_template - (optional) is a type of number
      shared_partition_http_template = port_list.value["shared_partition_http_template"]
      # shared_partition_persist_cookie_template - (optional) is a type of number
      shared_partition_persist_cookie_template = port_list.value["shared_partition_persist_cookie_template"]
      # shared_partition_persist_destination_ip_template - (optional) is a type of number
      shared_partition_persist_destination_ip_template = port_list.value["shared_partition_persist_destination_ip_template"]
      # shared_partition_persist_source_ip_template - (optional) is a type of number
      shared_partition_persist_source_ip_template = port_list.value["shared_partition_persist_source_ip_template"]
      # shared_partition_persist_ssl_sid_template - (optional) is a type of number
      shared_partition_persist_ssl_sid_template = port_list.value["shared_partition_persist_ssl_sid_template"]
      # shared_partition_policy_template - (optional) is a type of number
      shared_partition_policy_template = port_list.value["shared_partition_policy_template"]
      # shared_partition_pool - (optional) is a type of number
      shared_partition_pool = port_list.value["shared_partition_pool"]
      # shared_partition_server_ssl_template - (optional) is a type of number
      shared_partition_server_ssl_template = port_list.value["shared_partition_server_ssl_template"]
      # shared_partition_tcp - (optional) is a type of number
      shared_partition_tcp = port_list.value["shared_partition_tcp"]
      # shared_partition_tcp_proxy_template - (optional) is a type of number
      shared_partition_tcp_proxy_template = port_list.value["shared_partition_tcp_proxy_template"]
      # shared_partition_udp - (optional) is a type of number
      shared_partition_udp = port_list.value["shared_partition_udp"]
      # shared_partition_virtual_port_template - (optional) is a type of number
      shared_partition_virtual_port_template = port_list.value["shared_partition_virtual_port_template"]
      # skip_rev_hash - (optional) is a type of number
      skip_rev_hash = port_list.value["skip_rev_hash"]
      # snat_on_vip - (optional) is a type of number
      snat_on_vip = port_list.value["snat_on_vip"]
      # stats_data_action - (optional) is a type of string
      stats_data_action = port_list.value["stats_data_action"]
      # support_http2 - (optional) is a type of number
      support_http2 = port_list.value["support_http2"]
      # syn_cookie - (optional) is a type of number
      syn_cookie = port_list.value["syn_cookie"]
      # template_cache - (optional) is a type of string
      template_cache = port_list.value["template_cache"]
      # template_cache_shared - (optional) is a type of string
      template_cache_shared = port_list.value["template_cache_shared"]
      # template_client_ssh - (optional) is a type of string
      template_client_ssh = port_list.value["template_client_ssh"]
      # template_client_ssl - (optional) is a type of string
      template_client_ssl = port_list.value["template_client_ssl"]
      # template_client_ssl_shared - (optional) is a type of string
      template_client_ssl_shared = port_list.value["template_client_ssl_shared"]
      # template_connection_reuse - (optional) is a type of string
      template_connection_reuse = port_list.value["template_connection_reuse"]
      # template_connection_reuse_shared - (optional) is a type of string
      template_connection_reuse_shared = port_list.value["template_connection_reuse_shared"]
      # template_dblb - (optional) is a type of string
      template_dblb = port_list.value["template_dblb"]
      # template_diameter - (optional) is a type of string
      template_diameter = port_list.value["template_diameter"]
      # template_diameter_shared - (optional) is a type of string
      template_diameter_shared = port_list.value["template_diameter_shared"]
      # template_dns - (optional) is a type of string
      template_dns = port_list.value["template_dns"]
      # template_dns_shared - (optional) is a type of string
      template_dns_shared = port_list.value["template_dns_shared"]
      # template_dynamic_service - (optional) is a type of string
      template_dynamic_service = port_list.value["template_dynamic_service"]
      # template_dynamic_service_shared - (optional) is a type of string
      template_dynamic_service_shared = port_list.value["template_dynamic_service_shared"]
      # template_external_service - (optional) is a type of string
      template_external_service = port_list.value["template_external_service"]
      # template_external_service_shared - (optional) is a type of string
      template_external_service_shared = port_list.value["template_external_service_shared"]
      # template_file_inspection - (optional) is a type of string
      template_file_inspection = port_list.value["template_file_inspection"]
      # template_fix - (optional) is a type of string
      template_fix = port_list.value["template_fix"]
      # template_ftp - (optional) is a type of string
      template_ftp = port_list.value["template_ftp"]
      # template_http - (optional) is a type of string
      template_http = port_list.value["template_http"]
      # template_http_policy - (optional) is a type of string
      template_http_policy = port_list.value["template_http_policy"]
      # template_http_policy_shared - (optional) is a type of string
      template_http_policy_shared = port_list.value["template_http_policy_shared"]
      # template_http_shared - (optional) is a type of string
      template_http_shared = port_list.value["template_http_shared"]
      # template_imap_pop3 - (optional) is a type of string
      template_imap_pop3 = port_list.value["template_imap_pop3"]
      # template_persist_cookie - (optional) is a type of string
      template_persist_cookie = port_list.value["template_persist_cookie"]
      # template_persist_cookie_shared - (optional) is a type of string
      template_persist_cookie_shared = port_list.value["template_persist_cookie_shared"]
      # template_persist_destination_ip - (optional) is a type of string
      template_persist_destination_ip = port_list.value["template_persist_destination_ip"]
      # template_persist_destination_ip_shared - (optional) is a type of string
      template_persist_destination_ip_shared = port_list.value["template_persist_destination_ip_shared"]
      # template_persist_source_ip - (optional) is a type of string
      template_persist_source_ip = port_list.value["template_persist_source_ip"]
      # template_persist_source_ip_shared - (optional) is a type of string
      template_persist_source_ip_shared = port_list.value["template_persist_source_ip_shared"]
      # template_persist_ssl_sid - (optional) is a type of string
      template_persist_ssl_sid = port_list.value["template_persist_ssl_sid"]
      # template_persist_ssl_sid_shared - (optional) is a type of string
      template_persist_ssl_sid_shared = port_list.value["template_persist_ssl_sid_shared"]
      # template_policy - (optional) is a type of string
      template_policy = port_list.value["template_policy"]
      # template_policy_shared - (optional) is a type of string
      template_policy_shared = port_list.value["template_policy_shared"]
      # template_reqmod_icap - (optional) is a type of string
      template_reqmod_icap = port_list.value["template_reqmod_icap"]
      # template_respmod_icap - (optional) is a type of string
      template_respmod_icap = port_list.value["template_respmod_icap"]
      # template_scaleout - (optional) is a type of string
      template_scaleout = port_list.value["template_scaleout"]
      # template_server_ssh - (optional) is a type of string
      template_server_ssh = port_list.value["template_server_ssh"]
      # template_server_ssl - (optional) is a type of string
      template_server_ssl = port_list.value["template_server_ssl"]
      # template_server_ssl_shared - (optional) is a type of string
      template_server_ssl_shared = port_list.value["template_server_ssl_shared"]
      # template_sip - (optional) is a type of string
      template_sip = port_list.value["template_sip"]
      # template_smpp - (optional) is a type of string
      template_smpp = port_list.value["template_smpp"]
      # template_smtp - (optional) is a type of string
      template_smtp = port_list.value["template_smtp"]
      # template_ssli - (optional) is a type of string
      template_ssli = port_list.value["template_ssli"]
      # template_tcp - (optional) is a type of string
      template_tcp = port_list.value["template_tcp"]
      # template_tcp_proxy - (optional) is a type of string
      template_tcp_proxy = port_list.value["template_tcp_proxy"]
      # template_tcp_proxy_client - (optional) is a type of string
      template_tcp_proxy_client = port_list.value["template_tcp_proxy_client"]
      # template_tcp_proxy_server - (optional) is a type of string
      template_tcp_proxy_server = port_list.value["template_tcp_proxy_server"]
      # template_tcp_proxy_shared - (optional) is a type of string
      template_tcp_proxy_shared = port_list.value["template_tcp_proxy_shared"]
      # template_tcp_shared - (optional) is a type of string
      template_tcp_shared = port_list.value["template_tcp_shared"]
      # template_udp - (optional) is a type of string
      template_udp = port_list.value["template_udp"]
      # template_udp_shared - (optional) is a type of string
      template_udp_shared = port_list.value["template_udp_shared"]
      # template_virtual_port - (optional) is a type of string
      template_virtual_port = port_list.value["template_virtual_port"]
      # template_virtual_port_shared - (optional) is a type of string
      template_virtual_port_shared = port_list.value["template_virtual_port_shared"]
      # trunk_fwd - (optional) is a type of number
      trunk_fwd = port_list.value["trunk_fwd"]
      # trunk_rev - (optional) is a type of number
      trunk_rev = port_list.value["trunk_rev"]
      # use_alternate_port - (optional) is a type of number
      use_alternate_port = port_list.value["use_alternate_port"]
      # use_cgnv6 - (optional) is a type of number
      use_cgnv6 = port_list.value["use_cgnv6"]
      # use_default_if_no_server - (optional) is a type of number
      use_default_if_no_server = port_list.value["use_default_if_no_server"]
      # use_rcv_hop_for_resp - (optional) is a type of number
      use_rcv_hop_for_resp = port_list.value["use_rcv_hop_for_resp"]
      # user_tag - (optional) is a type of string
      user_tag = port_list.value["user_tag"]
      # uuid - (optional) is a type of string
      uuid = port_list.value["uuid"]
      # view - (optional) is a type of number
      view = port_list.value["view"]
      # waf_template - (optional) is a type of string
      waf_template = port_list.value["waf_template"]
      # when_down - (optional) is a type of number
      when_down = port_list.value["when_down"]
      # when_down_protocol2 - (optional) is a type of number
      when_down_protocol2 = port_list.value["when_down_protocol2"]

      dynamic "acl_id_list" {
        for_each = port_list.value.acl_id_list
        content {
          # acl_id - (optional) is a type of number
          acl_id = acl_id_list.value["acl_id"]
          # acl_id_seq_num - (optional) is a type of number
          acl_id_seq_num = acl_id_list.value["acl_id_seq_num"]
          # acl_id_seq_num_shared - (optional) is a type of number
          acl_id_seq_num_shared = acl_id_list.value["acl_id_seq_num_shared"]
          # acl_id_src_nat_pool - (optional) is a type of string
          acl_id_src_nat_pool = acl_id_list.value["acl_id_src_nat_pool"]
          # acl_id_src_nat_pool_shared - (optional) is a type of string
          acl_id_src_nat_pool_shared = acl_id_list.value["acl_id_src_nat_pool_shared"]
          # shared_partition_pool_id - (optional) is a type of number
          shared_partition_pool_id = acl_id_list.value["shared_partition_pool_id"]
        }
      }

      dynamic "acl_name_list" {
        for_each = port_list.value.acl_name_list
        content {
          # acl_name - (optional) is a type of string
          acl_name = acl_name_list.value["acl_name"]
          # acl_name_seq_num - (optional) is a type of number
          acl_name_seq_num = acl_name_list.value["acl_name_seq_num"]
          # acl_name_seq_num_shared - (optional) is a type of number
          acl_name_seq_num_shared = acl_name_list.value["acl_name_seq_num_shared"]
          # acl_name_src_nat_pool - (optional) is a type of string
          acl_name_src_nat_pool = acl_name_list.value["acl_name_src_nat_pool"]
          # acl_name_src_nat_pool_shared - (optional) is a type of string
          acl_name_src_nat_pool_shared = acl_name_list.value["acl_name_src_nat_pool_shared"]
          # shared_partition_pool_name - (optional) is a type of number
          shared_partition_pool_name = acl_name_list.value["shared_partition_pool_name"]
        }
      }

      dynamic "aflex_scripts" {
        for_each = port_list.value.aflex_scripts
        content {
          # aflex - (optional) is a type of string
          aflex = aflex_scripts.value["aflex"]
          # aflex_shared - (optional) is a type of string
          aflex_shared = aflex_scripts.value["aflex_shared"]
        }
      }

      dynamic "auth_cfg" {
        for_each = port_list.value.auth_cfg
        content {
          # aaa_policy - (optional) is a type of string
          aaa_policy = auth_cfg.value["aaa_policy"]
        }
      }

      dynamic "sampling_enable" {
        for_each = port_list.value.sampling_enable
        content {
          # counters1 - (optional) is a type of string
          counters1 = sampling_enable.value["counters1"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_virtual_server.this.id
}

output "this" {
  value = thunder_virtual_server.this
}
```

[top](#index)