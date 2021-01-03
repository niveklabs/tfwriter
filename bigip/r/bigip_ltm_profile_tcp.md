# bigip_ltm_profile_tcp

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_profile_tcp" {
  source = "./modules/bigip/r/bigip_ltm_profile_tcp"

  # close_wait_timeout - (optional) is a type of number
  close_wait_timeout = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # deferred_accept - (optional) is a type of string
  deferred_accept = null
  # fast_open - (optional) is a type of string
  fast_open = null
  # finwait_2timeout - (optional) is a type of number
  finwait_2timeout = null
  # finwait_timeout - (optional) is a type of number
  finwait_timeout = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # keepalive_interval - (optional) is a type of number
  keepalive_interval = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "close_wait_timeout" {
  description = "(optional) - Number of seconds (default 5) connection will remain in LAST-ACK state before exiting. Value -1 means indefinite, limited by maximum retransmission timeout"
  type        = number
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Use the parent tcp profile"
  type        = string
  default     = null
}

variable "deferred_accept" {
  description = "(optional) - If enabled, ADC will defer allocating resources to a connection until some payload data has arrived from the client (default false). This may help minimize the impact of certain DoS attacks but adds undesirable latency under normal conditions. Note: ‘deferredAccept’ is incompatible with server-speaks-first application protocols,Default : disabled"
  type        = string
  default     = null
}

variable "fast_open" {
  description = "(optional) - If enabled (default), the system can use the TCP Fast Open protocol extension to reduce latency by sending payload data with initial SYN"
  type        = string
  default     = null
}

variable "finwait_2timeout" {
  description = "(optional) - Number of seconds (default 300) connection will remain in LAST-ACK state before closing. Value -1 means indefinite, limited by maximum retransmission timeout"
  type        = number
  default     = null
}

variable "finwait_timeout" {
  description = "(optional) - Number of seconds (default 5) connection will remain in FIN-WAIT-1 or closing state before exiting. Value -1 means indefinite, limited by maximum retransmission timeout"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional) - Number of seconds (default 300; may not be 0) connection may remain idle before it becomes eligible for deletion. Value -1 (not recommended) means infinite"
  type        = number
  default     = null
}

variable "keepalive_interval" {
  description = "(optional) - Number of seconds (default 1800) between keep-alive probes"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the TCP Profile"
  type        = string
}

variable "partition" {
  description = "(optional) - name of partition"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_tcp" "this" {
  close_wait_timeout = var.close_wait_timeout
  defaults_from      = var.defaults_from
  deferred_accept    = var.deferred_accept
  fast_open          = var.fast_open
  finwait_2timeout   = var.finwait_2timeout
  finwait_timeout    = var.finwait_timeout
  idle_timeout       = var.idle_timeout
  keepalive_interval = var.keepalive_interval
  name               = var.name
  partition          = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "close_wait_timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_tcp.this.close_wait_timeout
}

output "defaults_from" {
  description = "returns a string"
  value       = bigip_ltm_profile_tcp.this.defaults_from
}

output "deferred_accept" {
  description = "returns a string"
  value       = bigip_ltm_profile_tcp.this.deferred_accept
}

output "fast_open" {
  description = "returns a string"
  value       = bigip_ltm_profile_tcp.this.fast_open
}

output "finwait_2timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_tcp.this.finwait_2timeout
}

output "finwait_timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_tcp.this.finwait_timeout
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_tcp.this.id
}

output "idle_timeout" {
  description = "returns a number"
  value       = bigip_ltm_profile_tcp.this.idle_timeout
}

output "keepalive_interval" {
  description = "returns a number"
  value       = bigip_ltm_profile_tcp.this.keepalive_interval
}

output "this" {
  value = bigip_ltm_profile_tcp.this
}
```

[top](#index)