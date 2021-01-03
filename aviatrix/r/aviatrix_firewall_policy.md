# aviatrix_firewall_policy

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firewall_policy" {
  source = "./modules/aviatrix/r/aviatrix_firewall_policy"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # dst_ip - (required) is a type of string
  dst_ip = null
  # gw_name - (required) is a type of string
  gw_name = null
  # log_enabled - (optional) is a type of bool
  log_enabled = null
  # port - (required) is a type of string
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # src_ip - (required) is a type of string
  src_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required) - Valid values: 'allow', 'deny' or 'force-drop'(in stateful firewall rule to allow immediate packet dropping on established sessions)."
  type        = string
}

variable "description" {
  description = "(optional) - Description of this firewall policy."
  type        = string
  default     = null
}

variable "dst_ip" {
  description = "(required) - CIDRs separated by comma or tag names such 'HR' or 'marketing' etc."
  type        = string
}

variable "gw_name" {
  description = "(required) - The name of gateway."
  type        = string
}

variable "log_enabled" {
  description = "(optional) - Valid values: true or false."
  type        = bool
  default     = null
}

variable "port" {
  description = "(required) - A single port or a range of port numbers."
  type        = string
}

variable "protocol" {
  description = "(optional) - 'all', 'tcp', 'udp', 'icmp', 'sctp', 'rdp', 'dccp'."
  type        = string
  default     = null
}

variable "src_ip" {
  description = "(required) - CIDRs separated by comma or tag names such 'HR' or 'marketing' etc."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firewall_policy" "this" {
  action      = var.action
  description = var.description
  dst_ip      = var.dst_ip
  gw_name     = var.gw_name
  log_enabled = var.log_enabled
  port        = var.port
  protocol    = var.protocol
  src_ip      = var.src_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_firewall_policy.this.id
}

output "this" {
  value = aviatrix_firewall_policy.this
}
```

[top](#index)