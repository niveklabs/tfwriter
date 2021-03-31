# fortios_fmg_firewall_object_service

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
module "fortios_fmg_firewall_object_service" {
  source = "./modules/fortios/r/fortios_fmg_firewall_object_service"

  # adom - (optional) is a type of string
  adom = null
  # category - (optional) is a type of string
  category = null
  # comment - (optional) is a type of string
  comment = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # icmp_code - (optional) is a type of number
  icmp_code = null
  # icmp_type - (optional) is a type of number
  icmp_type = null
  # iprange - (optional) is a type of string
  iprange = null
  # name - (required) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # protocol_number - (optional) is a type of number
  protocol_number = null
  # proxy - (optional) is a type of string
  proxy = null
  # sctp_portrange - (optional) is a type of list of string
  sctp_portrange = []
  # tcp_portrange - (optional) is a type of list of string
  tcp_portrange = []
  # udp_portrange - (optional) is a type of list of string
  udp_portrange = []
}
```

[top](#index)

### Variables

```terraform
variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmp_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iprange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sctp_portrange" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tcp_portrange" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "udp_portrange" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_firewall_object_service" "this" {
  adom            = var.adom
  category        = var.category
  comment         = var.comment
  fqdn            = var.fqdn
  icmp_code       = var.icmp_code
  icmp_type       = var.icmp_type
  iprange         = var.iprange
  name            = var.name
  protocol        = var.protocol
  protocol_number = var.protocol_number
  proxy           = var.proxy
  sctp_portrange  = var.sctp_portrange
  tcp_portrange   = var.tcp_portrange
  udp_portrange   = var.udp_portrange
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_firewall_object_service.this.id
}

output "this" {
  value = fortios_fmg_firewall_object_service.this
}
```

[top](#index)