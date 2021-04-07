# avi_networkprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_networkprofile" {
  source = "./modules/avi/r/avi_networkprofile"

  # connection_mirror - (optional) is a type of bool
  connection_mirror = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  profile = [{
    tcp_fast_path_profile = [{
      dsr_profile = [{
        dsr_encap_type = null
        dsr_type       = null
      }]
      enable_syn_protection = null
      session_idle_timeout  = null
    }]
    tcp_proxy_profile = [{
      aggressive_congestion_avoidance    = null
      automatic                          = null
      cc_algo                            = null
      congestion_recovery_scaling_factor = null
      idle_connection_timeout            = null
      idle_connection_type               = null
      ignore_time_wait                   = null
      ip_dscp                            = null
      keepalive_in_halfclose_state       = null
      max_retransmissions                = null
      max_segment_size                   = null
      max_syn_retransmissions            = null
      min_rexmt_timeout                  = null
      nagles_algorithm                   = null
      reassembly_queue_size              = null
      receive_window                     = null
      reorder_threshold                  = null
      slow_start_scaling_factor          = null
      time_wait_delay                    = null
      use_interface_mtu                  = null
    }]
    type = null
    udp_fast_path_profile = [{
      dsr_profile = [{
        dsr_encap_type = null
        dsr_type       = null
      }]
      per_pkt_loadbalance  = null
      session_idle_timeout = null
      snat                 = null
    }]
    udp_proxy_profile = [{
      session_idle_timeout = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connection_mirror" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      tcp_fast_path_profile = set(object(
        {
          dsr_profile = set(object(
            {
              dsr_encap_type = string
              dsr_type       = string
            }
          ))
          enable_syn_protection = bool
          session_idle_timeout  = number
        }
      ))
      tcp_proxy_profile = set(object(
        {
          aggressive_congestion_avoidance    = bool
          automatic                          = bool
          cc_algo                            = string
          congestion_recovery_scaling_factor = number
          idle_connection_timeout            = number
          idle_connection_type               = string
          ignore_time_wait                   = bool
          ip_dscp                            = number
          keepalive_in_halfclose_state       = bool
          max_retransmissions                = number
          max_segment_size                   = number
          max_syn_retransmissions            = number
          min_rexmt_timeout                  = number
          nagles_algorithm                   = bool
          reassembly_queue_size              = number
          receive_window                     = number
          reorder_threshold                  = number
          slow_start_scaling_factor          = number
          time_wait_delay                    = number
          use_interface_mtu                  = bool
        }
      ))
      type = string
      udp_fast_path_profile = set(object(
        {
          dsr_profile = set(object(
            {
              dsr_encap_type = string
              dsr_type       = string
            }
          ))
          per_pkt_loadbalance  = bool
          session_idle_timeout = number
          snat                 = bool
        }
      ))
      udp_proxy_profile = set(object(
        {
          session_idle_timeout = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "avi_networkprofile" "this" {
  # connection_mirror - (optional) is a type of bool
  connection_mirror = var.connection_mirror
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "profile" {
    for_each = var.profile
    content {
      # type - (required) is a type of string
      type = profile.value["type"]

      dynamic "tcp_fast_path_profile" {
        for_each = profile.value.tcp_fast_path_profile
        content {
          # enable_syn_protection - (optional) is a type of bool
          enable_syn_protection = tcp_fast_path_profile.value["enable_syn_protection"]
          # session_idle_timeout - (optional) is a type of number
          session_idle_timeout = tcp_fast_path_profile.value["session_idle_timeout"]

          dynamic "dsr_profile" {
            for_each = tcp_fast_path_profile.value.dsr_profile
            content {
              # dsr_encap_type - (optional) is a type of string
              dsr_encap_type = dsr_profile.value["dsr_encap_type"]
              # dsr_type - (optional) is a type of string
              dsr_type = dsr_profile.value["dsr_type"]
            }
          }

        }
      }

      dynamic "tcp_proxy_profile" {
        for_each = profile.value.tcp_proxy_profile
        content {
          # aggressive_congestion_avoidance - (optional) is a type of bool
          aggressive_congestion_avoidance = tcp_proxy_profile.value["aggressive_congestion_avoidance"]
          # automatic - (optional) is a type of bool
          automatic = tcp_proxy_profile.value["automatic"]
          # cc_algo - (optional) is a type of string
          cc_algo = tcp_proxy_profile.value["cc_algo"]
          # congestion_recovery_scaling_factor - (optional) is a type of number
          congestion_recovery_scaling_factor = tcp_proxy_profile.value["congestion_recovery_scaling_factor"]
          # idle_connection_timeout - (optional) is a type of number
          idle_connection_timeout = tcp_proxy_profile.value["idle_connection_timeout"]
          # idle_connection_type - (optional) is a type of string
          idle_connection_type = tcp_proxy_profile.value["idle_connection_type"]
          # ignore_time_wait - (optional) is a type of bool
          ignore_time_wait = tcp_proxy_profile.value["ignore_time_wait"]
          # ip_dscp - (optional) is a type of number
          ip_dscp = tcp_proxy_profile.value["ip_dscp"]
          # keepalive_in_halfclose_state - (optional) is a type of bool
          keepalive_in_halfclose_state = tcp_proxy_profile.value["keepalive_in_halfclose_state"]
          # max_retransmissions - (optional) is a type of number
          max_retransmissions = tcp_proxy_profile.value["max_retransmissions"]
          # max_segment_size - (optional) is a type of number
          max_segment_size = tcp_proxy_profile.value["max_segment_size"]
          # max_syn_retransmissions - (optional) is a type of number
          max_syn_retransmissions = tcp_proxy_profile.value["max_syn_retransmissions"]
          # min_rexmt_timeout - (optional) is a type of number
          min_rexmt_timeout = tcp_proxy_profile.value["min_rexmt_timeout"]
          # nagles_algorithm - (optional) is a type of bool
          nagles_algorithm = tcp_proxy_profile.value["nagles_algorithm"]
          # reassembly_queue_size - (optional) is a type of number
          reassembly_queue_size = tcp_proxy_profile.value["reassembly_queue_size"]
          # receive_window - (optional) is a type of number
          receive_window = tcp_proxy_profile.value["receive_window"]
          # reorder_threshold - (optional) is a type of number
          reorder_threshold = tcp_proxy_profile.value["reorder_threshold"]
          # slow_start_scaling_factor - (optional) is a type of number
          slow_start_scaling_factor = tcp_proxy_profile.value["slow_start_scaling_factor"]
          # time_wait_delay - (optional) is a type of number
          time_wait_delay = tcp_proxy_profile.value["time_wait_delay"]
          # use_interface_mtu - (optional) is a type of bool
          use_interface_mtu = tcp_proxy_profile.value["use_interface_mtu"]
        }
      }

      dynamic "udp_fast_path_profile" {
        for_each = profile.value.udp_fast_path_profile
        content {
          # per_pkt_loadbalance - (optional) is a type of bool
          per_pkt_loadbalance = udp_fast_path_profile.value["per_pkt_loadbalance"]
          # session_idle_timeout - (optional) is a type of number
          session_idle_timeout = udp_fast_path_profile.value["session_idle_timeout"]
          # snat - (optional) is a type of bool
          snat = udp_fast_path_profile.value["snat"]

          dynamic "dsr_profile" {
            for_each = udp_fast_path_profile.value.dsr_profile
            content {
              # dsr_encap_type - (optional) is a type of string
              dsr_encap_type = dsr_profile.value["dsr_encap_type"]
              # dsr_type - (optional) is a type of string
              dsr_type = dsr_profile.value["dsr_type"]
            }
          }

        }
      }

      dynamic "udp_proxy_profile" {
        for_each = profile.value.udp_proxy_profile
        content {
          # session_idle_timeout - (optional) is a type of number
          session_idle_timeout = udp_proxy_profile.value["session_idle_timeout"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_networkprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_networkprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_networkprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_networkprofile.this.uuid
}

output "this" {
  value = avi_networkprofile.this
}
```

[top](#index)