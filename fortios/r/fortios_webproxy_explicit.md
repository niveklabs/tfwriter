# fortios_webproxy_explicit

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
module "fortios_webproxy_explicit" {
  source = "./modules/fortios/r/fortios_webproxy_explicit"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ftp_incoming_port - (optional) is a type of string
  ftp_incoming_port = null
  # ftp_over_http - (optional) is a type of string
  ftp_over_http = null
  # http_incoming_port - (optional) is a type of string
  http_incoming_port = null
  # https_incoming_port - (optional) is a type of string
  https_incoming_port = null
  # https_replacement_message - (optional) is a type of string
  https_replacement_message = null
  # incoming_ip - (optional) is a type of string
  incoming_ip = null
  # incoming_ip6 - (optional) is a type of string
  incoming_ip6 = null
  # ipv6_status - (optional) is a type of string
  ipv6_status = null
  # message_upon_server_error - (optional) is a type of string
  message_upon_server_error = null
  # outgoing_ip - (optional) is a type of string
  outgoing_ip = null
  # outgoing_ip6 - (optional) is a type of string
  outgoing_ip6 = null
  # pac_file_data - (optional) is a type of string
  pac_file_data = null
  # pac_file_name - (optional) is a type of string
  pac_file_name = null
  # pac_file_server_port - (optional) is a type of string
  pac_file_server_port = null
  # pac_file_server_status - (optional) is a type of string
  pac_file_server_status = null
  # pac_file_url - (optional) is a type of string
  pac_file_url = null
  # pref_dns_result - (optional) is a type of string
  pref_dns_result = null
  # realm - (optional) is a type of string
  realm = null
  # sec_default_action - (optional) is a type of string
  sec_default_action = null
  # socks - (optional) is a type of string
  socks = null
  # socks_incoming_port - (optional) is a type of string
  socks_incoming_port = null
  # ssl_algorithm - (optional) is a type of string
  ssl_algorithm = null
  # status - (optional) is a type of string
  status = null
  # strict_guest - (optional) is a type of string
  strict_guest = null
  # trace_auth_no_rsp - (optional) is a type of string
  trace_auth_no_rsp = null
  # unknown_http_version - (optional) is a type of string
  unknown_http_version = null

  pac_policy = [{
    comments = null
    dstaddr = [{
      name = null
    }]
    pac_file_data = null
    pac_file_name = null
    policyid      = null
    srcaddr = [{
      name = null
    }]
    srcaddr6 = [{
      name = null
    }]
    status = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftp_incoming_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftp_over_http" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_incoming_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_incoming_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_replacement_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "incoming_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "incoming_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "message_upon_server_error" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outgoing_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outgoing_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pac_file_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pac_file_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pac_file_server_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pac_file_server_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pac_file_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pref_dns_result" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "realm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sec_default_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "socks" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "socks_incoming_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_guest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trace_auth_no_rsp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unknown_http_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pac_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comments = string
      dstaddr = list(object(
        {
          name = string
        }
      ))
      pac_file_data = string
      pac_file_name = string
      policyid      = number
      srcaddr = list(object(
        {
          name = string
        }
      ))
      srcaddr6 = list(object(
        {
          name = string
        }
      ))
      status = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webproxy_explicit" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # ftp_incoming_port - (optional) is a type of string
  ftp_incoming_port = var.ftp_incoming_port
  # ftp_over_http - (optional) is a type of string
  ftp_over_http = var.ftp_over_http
  # http_incoming_port - (optional) is a type of string
  http_incoming_port = var.http_incoming_port
  # https_incoming_port - (optional) is a type of string
  https_incoming_port = var.https_incoming_port
  # https_replacement_message - (optional) is a type of string
  https_replacement_message = var.https_replacement_message
  # incoming_ip - (optional) is a type of string
  incoming_ip = var.incoming_ip
  # incoming_ip6 - (optional) is a type of string
  incoming_ip6 = var.incoming_ip6
  # ipv6_status - (optional) is a type of string
  ipv6_status = var.ipv6_status
  # message_upon_server_error - (optional) is a type of string
  message_upon_server_error = var.message_upon_server_error
  # outgoing_ip - (optional) is a type of string
  outgoing_ip = var.outgoing_ip
  # outgoing_ip6 - (optional) is a type of string
  outgoing_ip6 = var.outgoing_ip6
  # pac_file_data - (optional) is a type of string
  pac_file_data = var.pac_file_data
  # pac_file_name - (optional) is a type of string
  pac_file_name = var.pac_file_name
  # pac_file_server_port - (optional) is a type of string
  pac_file_server_port = var.pac_file_server_port
  # pac_file_server_status - (optional) is a type of string
  pac_file_server_status = var.pac_file_server_status
  # pac_file_url - (optional) is a type of string
  pac_file_url = var.pac_file_url
  # pref_dns_result - (optional) is a type of string
  pref_dns_result = var.pref_dns_result
  # realm - (optional) is a type of string
  realm = var.realm
  # sec_default_action - (optional) is a type of string
  sec_default_action = var.sec_default_action
  # socks - (optional) is a type of string
  socks = var.socks
  # socks_incoming_port - (optional) is a type of string
  socks_incoming_port = var.socks_incoming_port
  # ssl_algorithm - (optional) is a type of string
  ssl_algorithm = var.ssl_algorithm
  # status - (optional) is a type of string
  status = var.status
  # strict_guest - (optional) is a type of string
  strict_guest = var.strict_guest
  # trace_auth_no_rsp - (optional) is a type of string
  trace_auth_no_rsp = var.trace_auth_no_rsp
  # unknown_http_version - (optional) is a type of string
  unknown_http_version = var.unknown_http_version

  dynamic "pac_policy" {
    for_each = var.pac_policy
    content {
      # comments - (optional) is a type of string
      comments = pac_policy.value["comments"]
      # pac_file_data - (optional) is a type of string
      pac_file_data = pac_policy.value["pac_file_data"]
      # pac_file_name - (optional) is a type of string
      pac_file_name = pac_policy.value["pac_file_name"]
      # policyid - (optional) is a type of number
      policyid = pac_policy.value["policyid"]
      # status - (optional) is a type of string
      status = pac_policy.value["status"]

      dynamic "dstaddr" {
        for_each = pac_policy.value.dstaddr
        content {
          # name - (optional) is a type of string
          name = dstaddr.value["name"]
        }
      }

      dynamic "srcaddr" {
        for_each = pac_policy.value.srcaddr
        content {
          # name - (optional) is a type of string
          name = srcaddr.value["name"]
        }
      }

      dynamic "srcaddr6" {
        for_each = pac_policy.value.srcaddr6
        content {
          # name - (optional) is a type of string
          name = srcaddr6.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ftp_incoming_port" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.ftp_incoming_port
}

output "ftp_over_http" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.ftp_over_http
}

output "http_incoming_port" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.http_incoming_port
}

output "https_incoming_port" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.https_incoming_port
}

output "https_replacement_message" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.https_replacement_message
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.id
}

output "incoming_ip" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.incoming_ip
}

output "incoming_ip6" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.incoming_ip6
}

output "ipv6_status" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.ipv6_status
}

output "message_upon_server_error" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.message_upon_server_error
}

output "outgoing_ip" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.outgoing_ip
}

output "outgoing_ip6" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.outgoing_ip6
}

output "pac_file_data" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.pac_file_data
}

output "pac_file_name" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.pac_file_name
}

output "pac_file_server_port" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.pac_file_server_port
}

output "pac_file_server_status" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.pac_file_server_status
}

output "pac_file_url" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.pac_file_url
}

output "pref_dns_result" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.pref_dns_result
}

output "realm" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.realm
}

output "sec_default_action" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.sec_default_action
}

output "socks" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.socks
}

output "socks_incoming_port" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.socks_incoming_port
}

output "ssl_algorithm" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.ssl_algorithm
}

output "status" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.status
}

output "strict_guest" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.strict_guest
}

output "trace_auth_no_rsp" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.trace_auth_no_rsp
}

output "unknown_http_version" {
  description = "returns a string"
  value       = fortios_webproxy_explicit.this.unknown_http_version
}

output "this" {
  value = fortios_webproxy_explicit.this
}
```

[top](#index)