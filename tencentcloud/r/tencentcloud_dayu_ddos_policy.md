# tencentcloud_dayu_ddos_policy

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_dayu_ddos_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_ddos_policy"

  # black_ips - (optional) is a type of set of string
  black_ips = []
  # name - (required) is a type of string
  name = null
  # resource_type - (required) is a type of string
  resource_type = null
  # white_ips - (optional) is a type of set of string
  white_ips = []

  drop_options = [{
    bad_conn_threshold = null
    check_sync_conn    = null
    conn_timeout       = null
    d_conn_limit       = null
    d_new_limit        = null
    drop_abroad        = null
    drop_icmp          = null
    drop_other         = null
    drop_tcp           = null
    drop_udp           = null
    icmp_mbps_limit    = null
    null_conn_enable   = null
    other_mbps_limit   = null
    s_conn_limit       = null
    s_new_limit        = null
    syn_limit          = null
    syn_rate           = null
    tcp_mbps_limit     = null
    udp_mbps_limit     = null
  }]

  packet_filters = [{
    action         = null
    d_end_port     = null
    d_start_port   = null
    depth          = null
    is_include     = null
    match_begin    = null
    match_str      = null
    match_type     = null
    offset         = null
    pkt_length_max = null
    pkt_length_min = null
    protocol       = null
    s_end_port     = null
    s_start_port   = null
  }]

  port_filters = [{
    action     = null
    end_port   = null
    kind       = null
    protocol   = null
    start_port = null
  }]

  watermark_filters = [{
    auto_remove   = null
    offset        = null
    open_switch   = null
    tcp_port_list = []
    udp_port_list = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "black_ips" {
  description = "(optional) - Black IP list."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the DDoS policy. Length should between 1 and 32."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the DDoS policy works for. Valid values: `bgpip`, `bgp`, `bgp-multip` and `net`."
  type        = string
}

variable "white_ips" {
  description = "(optional) - White IP list."
  type        = set(string)
  default     = null
}

variable "drop_options" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      bad_conn_threshold = number
      check_sync_conn    = bool
      conn_timeout       = number
      d_conn_limit       = number
      d_new_limit        = number
      drop_abroad        = bool
      drop_icmp          = bool
      drop_other         = bool
      drop_tcp           = bool
      drop_udp           = bool
      icmp_mbps_limit    = number
      null_conn_enable   = bool
      other_mbps_limit   = number
      s_conn_limit       = number
      s_new_limit        = number
      syn_limit          = number
      syn_rate           = number
      tcp_mbps_limit     = number
      udp_mbps_limit     = number
    }
  ))
}

variable "packet_filters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action         = string
      d_end_port     = number
      d_start_port   = number
      depth          = number
      is_include     = bool
      match_begin    = string
      match_str      = string
      match_type     = string
      offset         = number
      pkt_length_max = number
      pkt_length_min = number
      protocol       = string
      s_end_port     = number
      s_start_port   = number
    }
  ))
  default = []
}

variable "port_filters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action     = string
      end_port   = number
      kind       = number
      protocol   = string
      start_port = number
    }
  ))
  default = []
}

variable "watermark_filters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_remove   = bool
      offset        = number
      open_switch   = bool
      tcp_port_list = list(string)
      udp_port_list = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_ddos_policy" "this" {
  # black_ips - (optional) is a type of set of string
  black_ips = var.black_ips
  # name - (required) is a type of string
  name = var.name
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
  # white_ips - (optional) is a type of set of string
  white_ips = var.white_ips

  dynamic "drop_options" {
    for_each = var.drop_options
    content {
      # bad_conn_threshold - (required) is a type of number
      bad_conn_threshold = drop_options.value["bad_conn_threshold"]
      # check_sync_conn - (required) is a type of bool
      check_sync_conn = drop_options.value["check_sync_conn"]
      # conn_timeout - (required) is a type of number
      conn_timeout = drop_options.value["conn_timeout"]
      # d_conn_limit - (required) is a type of number
      d_conn_limit = drop_options.value["d_conn_limit"]
      # d_new_limit - (required) is a type of number
      d_new_limit = drop_options.value["d_new_limit"]
      # drop_abroad - (required) is a type of bool
      drop_abroad = drop_options.value["drop_abroad"]
      # drop_icmp - (required) is a type of bool
      drop_icmp = drop_options.value["drop_icmp"]
      # drop_other - (required) is a type of bool
      drop_other = drop_options.value["drop_other"]
      # drop_tcp - (required) is a type of bool
      drop_tcp = drop_options.value["drop_tcp"]
      # drop_udp - (required) is a type of bool
      drop_udp = drop_options.value["drop_udp"]
      # icmp_mbps_limit - (required) is a type of number
      icmp_mbps_limit = drop_options.value["icmp_mbps_limit"]
      # null_conn_enable - (required) is a type of bool
      null_conn_enable = drop_options.value["null_conn_enable"]
      # other_mbps_limit - (required) is a type of number
      other_mbps_limit = drop_options.value["other_mbps_limit"]
      # s_conn_limit - (required) is a type of number
      s_conn_limit = drop_options.value["s_conn_limit"]
      # s_new_limit - (required) is a type of number
      s_new_limit = drop_options.value["s_new_limit"]
      # syn_limit - (required) is a type of number
      syn_limit = drop_options.value["syn_limit"]
      # syn_rate - (optional) is a type of number
      syn_rate = drop_options.value["syn_rate"]
      # tcp_mbps_limit - (required) is a type of number
      tcp_mbps_limit = drop_options.value["tcp_mbps_limit"]
      # udp_mbps_limit - (required) is a type of number
      udp_mbps_limit = drop_options.value["udp_mbps_limit"]
    }
  }

  dynamic "packet_filters" {
    for_each = var.packet_filters
    content {
      # action - (optional) is a type of string
      action = packet_filters.value["action"]
      # d_end_port - (optional) is a type of number
      d_end_port = packet_filters.value["d_end_port"]
      # d_start_port - (optional) is a type of number
      d_start_port = packet_filters.value["d_start_port"]
      # depth - (optional) is a type of number
      depth = packet_filters.value["depth"]
      # is_include - (optional) is a type of bool
      is_include = packet_filters.value["is_include"]
      # match_begin - (optional) is a type of string
      match_begin = packet_filters.value["match_begin"]
      # match_str - (optional) is a type of string
      match_str = packet_filters.value["match_str"]
      # match_type - (optional) is a type of string
      match_type = packet_filters.value["match_type"]
      # offset - (optional) is a type of number
      offset = packet_filters.value["offset"]
      # pkt_length_max - (optional) is a type of number
      pkt_length_max = packet_filters.value["pkt_length_max"]
      # pkt_length_min - (optional) is a type of number
      pkt_length_min = packet_filters.value["pkt_length_min"]
      # protocol - (optional) is a type of string
      protocol = packet_filters.value["protocol"]
      # s_end_port - (optional) is a type of number
      s_end_port = packet_filters.value["s_end_port"]
      # s_start_port - (optional) is a type of number
      s_start_port = packet_filters.value["s_start_port"]
    }
  }

  dynamic "port_filters" {
    for_each = var.port_filters
    content {
      # action - (optional) is a type of string
      action = port_filters.value["action"]
      # end_port - (optional) is a type of number
      end_port = port_filters.value["end_port"]
      # kind - (optional) is a type of number
      kind = port_filters.value["kind"]
      # protocol - (optional) is a type of string
      protocol = port_filters.value["protocol"]
      # start_port - (optional) is a type of number
      start_port = port_filters.value["start_port"]
    }
  }

  dynamic "watermark_filters" {
    for_each = var.watermark_filters
    content {
      # auto_remove - (optional) is a type of bool
      auto_remove = watermark_filters.value["auto_remove"]
      # offset - (optional) is a type of number
      offset = watermark_filters.value["offset"]
      # open_switch - (optional) is a type of bool
      open_switch = watermark_filters.value["open_switch"]
      # tcp_port_list - (optional) is a type of list of string
      tcp_port_list = watermark_filters.value["tcp_port_list"]
      # udp_port_list - (optional) is a type of list of string
      udp_port_list = watermark_filters.value["udp_port_list"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy.this.id
}

output "policy_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy.this.policy_id
}

output "scene_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy.this.scene_id
}

output "watermark_key" {
  description = "returns a list of object"
  value       = tencentcloud_dayu_ddos_policy.this.watermark_key
}

output "this" {
  value = tencentcloud_dayu_ddos_policy.this
}
```

[top](#index)