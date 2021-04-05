# thunder_slb_template_virtual_port

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
module "thunder_slb_template_virtual_port" {
  source = "./modules/thunder/r/thunder_slb_template_virtual_port"

  # aflow - (optional) is a type of number
  aflow = null
  # allow_syn_otherflags - (optional) is a type of number
  allow_syn_otherflags = null
  # allow_vip_to_rport_mapping - (optional) is a type of number
  allow_vip_to_rport_mapping = null
  # conn_limit - (optional) is a type of number
  conn_limit = null
  # conn_limit_no_logging - (optional) is a type of number
  conn_limit_no_logging = null
  # conn_limit_reset - (optional) is a type of number
  conn_limit_reset = null
  # conn_rate_limit - (optional) is a type of number
  conn_rate_limit = null
  # conn_rate_limit_no_logging - (optional) is a type of number
  conn_rate_limit_no_logging = null
  # conn_rate_limit_reset - (optional) is a type of number
  conn_rate_limit_reset = null
  # drop_unknown_conn - (optional) is a type of number
  drop_unknown_conn = null
  # dscp - (optional) is a type of number
  dscp = null
  # ignore_tcp_msl - (optional) is a type of number
  ignore_tcp_msl = null
  # log_options - (optional) is a type of string
  log_options = null
  # name - (optional) is a type of string
  name = null
  # non_syn_initiation - (optional) is a type of number
  non_syn_initiation = null
  # pkt_rate_interval - (optional) is a type of string
  pkt_rate_interval = null
  # pkt_rate_limit_reset - (optional) is a type of number
  pkt_rate_limit_reset = null
  # pkt_rate_type - (optional) is a type of string
  pkt_rate_type = null
  # rate - (optional) is a type of number
  rate = null
  # rate_interval - (optional) is a type of string
  rate_interval = null
  # reset_l7_on_failover - (optional) is a type of number
  reset_l7_on_failover = null
  # reset_unknown_conn - (optional) is a type of number
  reset_unknown_conn = null
  # snat_msl - (optional) is a type of number
  snat_msl = null
  # snat_port_preserve - (optional) is a type of number
  snat_port_preserve = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # when_rr_enable - (optional) is a type of number
  when_rr_enable = null
}
```

[top](#index)

### Variables

```terraform
variable "aflow" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allow_syn_otherflags" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allow_vip_to_rport_mapping" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_limit_no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_limit_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_limit_no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_limit_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "drop_unknown_conn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ignore_tcp_msl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "non_syn_initiation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pkt_rate_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pkt_rate_limit_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pkt_rate_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rate_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reset_l7_on_failover" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_unknown_conn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat_msl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat_port_preserve" {
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

variable "when_rr_enable" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_virtual_port" "this" {
  aflow                      = var.aflow
  allow_syn_otherflags       = var.allow_syn_otherflags
  allow_vip_to_rport_mapping = var.allow_vip_to_rport_mapping
  conn_limit                 = var.conn_limit
  conn_limit_no_logging      = var.conn_limit_no_logging
  conn_limit_reset           = var.conn_limit_reset
  conn_rate_limit            = var.conn_rate_limit
  conn_rate_limit_no_logging = var.conn_rate_limit_no_logging
  conn_rate_limit_reset      = var.conn_rate_limit_reset
  drop_unknown_conn          = var.drop_unknown_conn
  dscp                       = var.dscp
  ignore_tcp_msl             = var.ignore_tcp_msl
  log_options                = var.log_options
  name                       = var.name
  non_syn_initiation         = var.non_syn_initiation
  pkt_rate_interval          = var.pkt_rate_interval
  pkt_rate_limit_reset       = var.pkt_rate_limit_reset
  pkt_rate_type              = var.pkt_rate_type
  rate                       = var.rate
  rate_interval              = var.rate_interval
  reset_l7_on_failover       = var.reset_l7_on_failover
  reset_unknown_conn         = var.reset_unknown_conn
  snat_msl                   = var.snat_msl
  snat_port_preserve         = var.snat_port_preserve
  user_tag                   = var.user_tag
  uuid                       = var.uuid
  when_rr_enable             = var.when_rr_enable
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_virtual_port.this.id
}

output "this" {
  value = thunder_slb_template_virtual_port.this
}
```

[top](#index)