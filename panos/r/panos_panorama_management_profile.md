# panos_panorama_management_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_management_profile" {
  source = "./modules/panos/r/panos_panorama_management_profile"

  # http - (optional) is a type of bool
  http = null
  # http_ocsp - (optional) is a type of bool
  http_ocsp = null
  # https - (optional) is a type of bool
  https = null
  # name - (required) is a type of string
  name = null
  # permitted_ips - (optional) is a type of list of string
  permitted_ips = []
  # ping - (optional) is a type of bool
  ping = null
  # response_pages - (optional) is a type of bool
  response_pages = null
  # snmp - (optional) is a type of bool
  snmp = null
  # ssh - (optional) is a type of bool
  ssh = null
  # telnet - (optional) is a type of bool
  telnet = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # userid_service - (optional) is a type of bool
  userid_service = null
  # userid_syslog_listener_ssl - (optional) is a type of bool
  userid_syslog_listener_ssl = null
  # userid_syslog_listener_udp - (optional) is a type of bool
  userid_syslog_listener_udp = null
}
```

[top](#index)

### Variables

```terraform
variable "http" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "http_ocsp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "https" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "permitted_ips" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ping" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "response_pages" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "snmp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssh" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "telnet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "userid_service" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "userid_syslog_listener_ssl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "userid_syslog_listener_udp" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_management_profile" "this" {
  http                       = var.http
  http_ocsp                  = var.http_ocsp
  https                      = var.https
  name                       = var.name
  permitted_ips              = var.permitted_ips
  ping                       = var.ping
  response_pages             = var.response_pages
  snmp                       = var.snmp
  ssh                        = var.ssh
  telnet                     = var.telnet
  template                   = var.template
  template_stack             = var.template_stack
  userid_service             = var.userid_service
  userid_syslog_listener_ssl = var.userid_syslog_listener_ssl
  userid_syslog_listener_udp = var.userid_syslog_listener_udp
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_management_profile.this.id
}

output "this" {
  value = panos_panorama_management_profile.this
}
```

[top](#index)