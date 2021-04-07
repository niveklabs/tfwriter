# thunder_slb_template_tcp_proxy

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
module "thunder_slb_template_tcp_proxy" {
  source = "./modules/thunder/r/thunder_slb_template_tcp_proxy"

  # ack_aggressiveness - (optional) is a type of string
  ack_aggressiveness = null
  # alive_if_active - (optional) is a type of number
  alive_if_active = null
  # backend_wscale - (optional) is a type of number
  backend_wscale = null
  # del_session_on_server_down - (optional) is a type of number
  del_session_on_server_down = null
  # disable - (optional) is a type of number
  disable = null
  # disable_abc - (optional) is a type of number
  disable_abc = null
  # disable_sack - (optional) is a type of number
  disable_sack = null
  # disable_tcp_timestamps - (optional) is a type of number
  disable_tcp_timestamps = null
  # disable_window_scale - (optional) is a type of number
  disable_window_scale = null
  # down - (optional) is a type of number
  down = null
  # dynamic_buffer_allocation - (optional) is a type of number
  dynamic_buffer_allocation = null
  # early_retransmit - (optional) is a type of number
  early_retransmit = null
  # fin_timeout - (optional) is a type of number
  fin_timeout = null
  # force_delete_timeout - (optional) is a type of number
  force_delete_timeout = null
  # force_delete_timeout_100ms - (optional) is a type of number
  force_delete_timeout_100ms = null
  # half_close_idle_timeout - (optional) is a type of number
  half_close_idle_timeout = null
  # half_open_idle_timeout - (optional) is a type of number
  half_open_idle_timeout = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # init_cwnd - (optional) is a type of number
  init_cwnd = null
  # initial_window_size - (optional) is a type of number
  initial_window_size = null
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = null
  # invalid_rate_limit - (optional) is a type of number
  invalid_rate_limit = null
  # keepalive_interval - (optional) is a type of number
  keepalive_interval = null
  # keepalive_probes - (optional) is a type of number
  keepalive_probes = null
  # limited_slowstart - (optional) is a type of number
  limited_slowstart = null
  # maxburst - (optional) is a type of number
  maxburst = null
  # min_rto - (optional) is a type of number
  min_rto = null
  # mss - (optional) is a type of number
  mss = null
  # nagle - (optional) is a type of number
  nagle = null
  # name - (optional) is a type of string
  name = null
  # psh_flag_optimization - (optional) is a type of number
  psh_flag_optimization = null
  # qos - (optional) is a type of number
  qos = null
  # reassembly_limit - (optional) is a type of number
  reassembly_limit = null
  # reassembly_timeout - (optional) is a type of number
  reassembly_timeout = null
  # receive_buffer - (optional) is a type of number
  receive_buffer = null
  # reno - (optional) is a type of number
  reno = null
  # reset_fwd - (optional) is a type of number
  reset_fwd = null
  # reset_rev - (optional) is a type of number
  reset_rev = null
  # retransmit_retries - (optional) is a type of number
  retransmit_retries = null
  # server_down_action - (optional) is a type of string
  server_down_action = null
  # syn_retries - (optional) is a type of number
  syn_retries = null
  # timewait - (optional) is a type of number
  timewait = null
  # transmit_buffer - (optional) is a type of number
  transmit_buffer = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "ack_aggressiveness" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alive_if_active" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backend_wscale" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "del_session_on_server_down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_abc" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_sack" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_tcp_timestamps" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_window_scale" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_buffer_allocation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "early_retransmit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fin_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "force_delete_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "force_delete_timeout_100ms" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "half_close_idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "half_open_idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "init_cwnd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "initial_window_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "insert_client_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "invalid_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keepalive_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keepalive_probes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "limited_slowstart" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maxburst" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_rto" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mss" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nagle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "psh_flag_optimization" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "qos" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reassembly_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reassembly_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "receive_buffer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reno" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_fwd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_rev" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retransmit_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_down_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syn_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timewait" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "transmit_buffer" {
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
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_tcp_proxy" "this" {
  # ack_aggressiveness - (optional) is a type of string
  ack_aggressiveness = var.ack_aggressiveness
  # alive_if_active - (optional) is a type of number
  alive_if_active = var.alive_if_active
  # backend_wscale - (optional) is a type of number
  backend_wscale = var.backend_wscale
  # del_session_on_server_down - (optional) is a type of number
  del_session_on_server_down = var.del_session_on_server_down
  # disable - (optional) is a type of number
  disable = var.disable
  # disable_abc - (optional) is a type of number
  disable_abc = var.disable_abc
  # disable_sack - (optional) is a type of number
  disable_sack = var.disable_sack
  # disable_tcp_timestamps - (optional) is a type of number
  disable_tcp_timestamps = var.disable_tcp_timestamps
  # disable_window_scale - (optional) is a type of number
  disable_window_scale = var.disable_window_scale
  # down - (optional) is a type of number
  down = var.down
  # dynamic_buffer_allocation - (optional) is a type of number
  dynamic_buffer_allocation = var.dynamic_buffer_allocation
  # early_retransmit - (optional) is a type of number
  early_retransmit = var.early_retransmit
  # fin_timeout - (optional) is a type of number
  fin_timeout = var.fin_timeout
  # force_delete_timeout - (optional) is a type of number
  force_delete_timeout = var.force_delete_timeout
  # force_delete_timeout_100ms - (optional) is a type of number
  force_delete_timeout_100ms = var.force_delete_timeout_100ms
  # half_close_idle_timeout - (optional) is a type of number
  half_close_idle_timeout = var.half_close_idle_timeout
  # half_open_idle_timeout - (optional) is a type of number
  half_open_idle_timeout = var.half_open_idle_timeout
  # idle_timeout - (optional) is a type of number
  idle_timeout = var.idle_timeout
  # init_cwnd - (optional) is a type of number
  init_cwnd = var.init_cwnd
  # initial_window_size - (optional) is a type of number
  initial_window_size = var.initial_window_size
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = var.insert_client_ip
  # invalid_rate_limit - (optional) is a type of number
  invalid_rate_limit = var.invalid_rate_limit
  # keepalive_interval - (optional) is a type of number
  keepalive_interval = var.keepalive_interval
  # keepalive_probes - (optional) is a type of number
  keepalive_probes = var.keepalive_probes
  # limited_slowstart - (optional) is a type of number
  limited_slowstart = var.limited_slowstart
  # maxburst - (optional) is a type of number
  maxburst = var.maxburst
  # min_rto - (optional) is a type of number
  min_rto = var.min_rto
  # mss - (optional) is a type of number
  mss = var.mss
  # nagle - (optional) is a type of number
  nagle = var.nagle
  # name - (optional) is a type of string
  name = var.name
  # psh_flag_optimization - (optional) is a type of number
  psh_flag_optimization = var.psh_flag_optimization
  # qos - (optional) is a type of number
  qos = var.qos
  # reassembly_limit - (optional) is a type of number
  reassembly_limit = var.reassembly_limit
  # reassembly_timeout - (optional) is a type of number
  reassembly_timeout = var.reassembly_timeout
  # receive_buffer - (optional) is a type of number
  receive_buffer = var.receive_buffer
  # reno - (optional) is a type of number
  reno = var.reno
  # reset_fwd - (optional) is a type of number
  reset_fwd = var.reset_fwd
  # reset_rev - (optional) is a type of number
  reset_rev = var.reset_rev
  # retransmit_retries - (optional) is a type of number
  retransmit_retries = var.retransmit_retries
  # server_down_action - (optional) is a type of string
  server_down_action = var.server_down_action
  # syn_retries - (optional) is a type of number
  syn_retries = var.syn_retries
  # timewait - (optional) is a type of number
  timewait = var.timewait
  # transmit_buffer - (optional) is a type of number
  transmit_buffer = var.transmit_buffer
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_tcp_proxy.this.id
}

output "this" {
  value = thunder_slb_template_tcp_proxy.this
}
```

[top](#index)