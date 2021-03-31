# fortios_firewall_profileprotocoloptions

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
module "fortios_firewall_profileprotocoloptions" {
  source = "./modules/fortios/r/fortios_firewall_profileprotocoloptions"

  # comment - (optional) is a type of string
  comment = null
  # feature_set - (optional) is a type of string
  feature_set = null
  # name - (required) is a type of string
  name = null
  # oversize_log - (optional) is a type of string
  oversize_log = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # rpc_over_http - (optional) is a type of string
  rpc_over_http = null
  # switching_protocols_log - (optional) is a type of string
  switching_protocols_log = null

  cifs = [{
    domain_controller      = null
    options                = null
    oversize_limit         = null
    ports                  = null
    scan_bzip2             = null
    server_credential_type = null
    server_keytab = [{
      keytab    = null
      principal = null
    }]
    status                      = null
    tcp_window_maximum          = null
    tcp_window_minimum          = null
    tcp_window_size             = null
    tcp_window_type             = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  dns = [{
    ports  = null
    status = null
  }]

  ftp = [{
    comfort_amount                  = null
    comfort_interval                = null
    inspect_all                     = null
    options                         = null
    oversize_limit                  = null
    ports                           = null
    scan_bzip2                      = null
    ssl_offloaded                   = null
    status                          = null
    stream_based_uncompressed_limit = null
    tcp_window_maximum              = null
    tcp_window_minimum              = null
    tcp_window_size                 = null
    tcp_window_type                 = null
    uncompressed_nest_limit         = null
    uncompressed_oversize_limit     = null
  }]

  http = [{
    block_page_status_code          = null
    comfort_amount                  = null
    comfort_interval                = null
    fortinet_bar                    = null
    fortinet_bar_port               = null
    http_policy                     = null
    inspect_all                     = null
    options                         = null
    oversize_limit                  = null
    ports                           = null
    post_lang                       = null
    proxy_after_tcp_handshake       = null
    range_block                     = null
    retry_count                     = null
    scan_bzip2                      = null
    ssl_offloaded                   = null
    status                          = null
    stream_based_uncompressed_limit = null
    streaming_content_bypass        = null
    strip_x_forwarded_for           = null
    switching_protocols             = null
    tcp_window_maximum              = null
    tcp_window_minimum              = null
    tcp_window_size                 = null
    tcp_window_type                 = null
    tunnel_non_http                 = null
    uncompressed_nest_limit         = null
    uncompressed_oversize_limit     = null
    unknown_http_version            = null
  }]

  imap = [{
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    scan_bzip2                  = null
    ssl_offloaded               = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  mail_signature = [{
    signature = null
    status    = null
  }]

  mapi = [{
    options                     = null
    oversize_limit              = null
    ports                       = null
    scan_bzip2                  = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  nntp = [{
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    scan_bzip2                  = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  pop3 = [{
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    scan_bzip2                  = null
    ssl_offloaded               = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  smtp = [{
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    proxy_after_tcp_handshake   = null
    scan_bzip2                  = null
    server_busy                 = null
    ssl_offloaded               = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  ssh = [{
    comfort_amount                  = null
    comfort_interval                = null
    options                         = null
    oversize_limit                  = null
    scan_bzip2                      = null
    ssl_offloaded                   = null
    stream_based_uncompressed_limit = null
    tcp_window_maximum              = null
    tcp_window_minimum              = null
    tcp_window_size                 = null
    tcp_window_type                 = null
    uncompressed_nest_limit         = null
    uncompressed_oversize_limit     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "feature_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "oversize_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rpc_over_http" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switching_protocols_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cifs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      domain_controller      = string
      options                = string
      oversize_limit         = number
      ports                  = number
      scan_bzip2             = string
      server_credential_type = string
      server_keytab = list(object(
        {
          keytab    = string
          principal = string
        }
      ))
      status                      = string
      tcp_window_maximum          = number
      tcp_window_minimum          = number
      tcp_window_size             = number
      tcp_window_type             = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
    }
  ))
  default = []
}

variable "dns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ports  = number
      status = string
    }
  ))
  default = []
}

variable "ftp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comfort_amount                  = number
      comfort_interval                = number
      inspect_all                     = string
      options                         = string
      oversize_limit                  = number
      ports                           = number
      scan_bzip2                      = string
      ssl_offloaded                   = string
      status                          = string
      stream_based_uncompressed_limit = number
      tcp_window_maximum              = number
      tcp_window_minimum              = number
      tcp_window_size                 = number
      tcp_window_type                 = string
      uncompressed_nest_limit         = number
      uncompressed_oversize_limit     = number
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      block_page_status_code          = number
      comfort_amount                  = number
      comfort_interval                = number
      fortinet_bar                    = string
      fortinet_bar_port               = number
      http_policy                     = string
      inspect_all                     = string
      options                         = string
      oversize_limit                  = number
      ports                           = number
      post_lang                       = string
      proxy_after_tcp_handshake       = string
      range_block                     = string
      retry_count                     = number
      scan_bzip2                      = string
      ssl_offloaded                   = string
      status                          = string
      stream_based_uncompressed_limit = number
      streaming_content_bypass        = string
      strip_x_forwarded_for           = string
      switching_protocols             = string
      tcp_window_maximum              = number
      tcp_window_minimum              = number
      tcp_window_size                 = number
      tcp_window_type                 = string
      tunnel_non_http                 = string
      uncompressed_nest_limit         = number
      uncompressed_oversize_limit     = number
      unknown_http_version            = string
    }
  ))
  default = []
}

variable "imap" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inspect_all                 = string
      options                     = string
      oversize_limit              = number
      ports                       = number
      proxy_after_tcp_handshake   = string
      scan_bzip2                  = string
      ssl_offloaded               = string
      status                      = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
    }
  ))
  default = []
}

variable "mail_signature" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      signature = string
      status    = string
    }
  ))
  default = []
}

variable "mapi" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      options                     = string
      oversize_limit              = number
      ports                       = number
      scan_bzip2                  = string
      status                      = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
    }
  ))
  default = []
}

variable "nntp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inspect_all                 = string
      options                     = string
      oversize_limit              = number
      ports                       = number
      proxy_after_tcp_handshake   = string
      scan_bzip2                  = string
      status                      = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
    }
  ))
  default = []
}

variable "pop3" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inspect_all                 = string
      options                     = string
      oversize_limit              = number
      ports                       = number
      proxy_after_tcp_handshake   = string
      scan_bzip2                  = string
      ssl_offloaded               = string
      status                      = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
    }
  ))
  default = []
}

variable "smtp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inspect_all                 = string
      options                     = string
      oversize_limit              = number
      ports                       = number
      proxy_after_tcp_handshake   = string
      scan_bzip2                  = string
      server_busy                 = string
      ssl_offloaded               = string
      status                      = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
    }
  ))
  default = []
}

variable "ssh" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comfort_amount                  = number
      comfort_interval                = number
      options                         = string
      oversize_limit                  = number
      scan_bzip2                      = string
      ssl_offloaded                   = string
      stream_based_uncompressed_limit = number
      tcp_window_maximum              = number
      tcp_window_minimum              = number
      tcp_window_size                 = number
      tcp_window_type                 = string
      uncompressed_nest_limit         = number
      uncompressed_oversize_limit     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_profileprotocoloptions" "this" {
  comment                 = var.comment
  feature_set             = var.feature_set
  name                    = var.name
  oversize_log            = var.oversize_log
  replacemsg_group        = var.replacemsg_group
  rpc_over_http           = var.rpc_over_http
  switching_protocols_log = var.switching_protocols_log

  dynamic "cifs" {
    for_each = var.cifs
    content {
      domain_controller           = cifs.value["domain_controller"]
      options                     = cifs.value["options"]
      oversize_limit              = cifs.value["oversize_limit"]
      ports                       = cifs.value["ports"]
      scan_bzip2                  = cifs.value["scan_bzip2"]
      server_credential_type      = cifs.value["server_credential_type"]
      status                      = cifs.value["status"]
      tcp_window_maximum          = cifs.value["tcp_window_maximum"]
      tcp_window_minimum          = cifs.value["tcp_window_minimum"]
      tcp_window_size             = cifs.value["tcp_window_size"]
      tcp_window_type             = cifs.value["tcp_window_type"]
      uncompressed_nest_limit     = cifs.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = cifs.value["uncompressed_oversize_limit"]

      dynamic "server_keytab" {
        for_each = cifs.value.server_keytab
        content {
          keytab    = server_keytab.value["keytab"]
          principal = server_keytab.value["principal"]
        }
      }

    }
  }

  dynamic "dns" {
    for_each = var.dns
    content {
      ports  = dns.value["ports"]
      status = dns.value["status"]
    }
  }

  dynamic "ftp" {
    for_each = var.ftp
    content {
      comfort_amount                  = ftp.value["comfort_amount"]
      comfort_interval                = ftp.value["comfort_interval"]
      inspect_all                     = ftp.value["inspect_all"]
      options                         = ftp.value["options"]
      oversize_limit                  = ftp.value["oversize_limit"]
      ports                           = ftp.value["ports"]
      scan_bzip2                      = ftp.value["scan_bzip2"]
      ssl_offloaded                   = ftp.value["ssl_offloaded"]
      status                          = ftp.value["status"]
      stream_based_uncompressed_limit = ftp.value["stream_based_uncompressed_limit"]
      tcp_window_maximum              = ftp.value["tcp_window_maximum"]
      tcp_window_minimum              = ftp.value["tcp_window_minimum"]
      tcp_window_size                 = ftp.value["tcp_window_size"]
      tcp_window_type                 = ftp.value["tcp_window_type"]
      uncompressed_nest_limit         = ftp.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit     = ftp.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      block_page_status_code          = http.value["block_page_status_code"]
      comfort_amount                  = http.value["comfort_amount"]
      comfort_interval                = http.value["comfort_interval"]
      fortinet_bar                    = http.value["fortinet_bar"]
      fortinet_bar_port               = http.value["fortinet_bar_port"]
      http_policy                     = http.value["http_policy"]
      inspect_all                     = http.value["inspect_all"]
      options                         = http.value["options"]
      oversize_limit                  = http.value["oversize_limit"]
      ports                           = http.value["ports"]
      post_lang                       = http.value["post_lang"]
      proxy_after_tcp_handshake       = http.value["proxy_after_tcp_handshake"]
      range_block                     = http.value["range_block"]
      retry_count                     = http.value["retry_count"]
      scan_bzip2                      = http.value["scan_bzip2"]
      ssl_offloaded                   = http.value["ssl_offloaded"]
      status                          = http.value["status"]
      stream_based_uncompressed_limit = http.value["stream_based_uncompressed_limit"]
      streaming_content_bypass        = http.value["streaming_content_bypass"]
      strip_x_forwarded_for           = http.value["strip_x_forwarded_for"]
      switching_protocols             = http.value["switching_protocols"]
      tcp_window_maximum              = http.value["tcp_window_maximum"]
      tcp_window_minimum              = http.value["tcp_window_minimum"]
      tcp_window_size                 = http.value["tcp_window_size"]
      tcp_window_type                 = http.value["tcp_window_type"]
      tunnel_non_http                 = http.value["tunnel_non_http"]
      uncompressed_nest_limit         = http.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit     = http.value["uncompressed_oversize_limit"]
      unknown_http_version            = http.value["unknown_http_version"]
    }
  }

  dynamic "imap" {
    for_each = var.imap
    content {
      inspect_all                 = imap.value["inspect_all"]
      options                     = imap.value["options"]
      oversize_limit              = imap.value["oversize_limit"]
      ports                       = imap.value["ports"]
      proxy_after_tcp_handshake   = imap.value["proxy_after_tcp_handshake"]
      scan_bzip2                  = imap.value["scan_bzip2"]
      ssl_offloaded               = imap.value["ssl_offloaded"]
      status                      = imap.value["status"]
      uncompressed_nest_limit     = imap.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = imap.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "mail_signature" {
    for_each = var.mail_signature
    content {
      signature = mail_signature.value["signature"]
      status    = mail_signature.value["status"]
    }
  }

  dynamic "mapi" {
    for_each = var.mapi
    content {
      options                     = mapi.value["options"]
      oversize_limit              = mapi.value["oversize_limit"]
      ports                       = mapi.value["ports"]
      scan_bzip2                  = mapi.value["scan_bzip2"]
      status                      = mapi.value["status"]
      uncompressed_nest_limit     = mapi.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = mapi.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "nntp" {
    for_each = var.nntp
    content {
      inspect_all                 = nntp.value["inspect_all"]
      options                     = nntp.value["options"]
      oversize_limit              = nntp.value["oversize_limit"]
      ports                       = nntp.value["ports"]
      proxy_after_tcp_handshake   = nntp.value["proxy_after_tcp_handshake"]
      scan_bzip2                  = nntp.value["scan_bzip2"]
      status                      = nntp.value["status"]
      uncompressed_nest_limit     = nntp.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = nntp.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "pop3" {
    for_each = var.pop3
    content {
      inspect_all                 = pop3.value["inspect_all"]
      options                     = pop3.value["options"]
      oversize_limit              = pop3.value["oversize_limit"]
      ports                       = pop3.value["ports"]
      proxy_after_tcp_handshake   = pop3.value["proxy_after_tcp_handshake"]
      scan_bzip2                  = pop3.value["scan_bzip2"]
      ssl_offloaded               = pop3.value["ssl_offloaded"]
      status                      = pop3.value["status"]
      uncompressed_nest_limit     = pop3.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = pop3.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "smtp" {
    for_each = var.smtp
    content {
      inspect_all                 = smtp.value["inspect_all"]
      options                     = smtp.value["options"]
      oversize_limit              = smtp.value["oversize_limit"]
      ports                       = smtp.value["ports"]
      proxy_after_tcp_handshake   = smtp.value["proxy_after_tcp_handshake"]
      scan_bzip2                  = smtp.value["scan_bzip2"]
      server_busy                 = smtp.value["server_busy"]
      ssl_offloaded               = smtp.value["ssl_offloaded"]
      status                      = smtp.value["status"]
      uncompressed_nest_limit     = smtp.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = smtp.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "ssh" {
    for_each = var.ssh
    content {
      comfort_amount                  = ssh.value["comfort_amount"]
      comfort_interval                = ssh.value["comfort_interval"]
      options                         = ssh.value["options"]
      oversize_limit                  = ssh.value["oversize_limit"]
      scan_bzip2                      = ssh.value["scan_bzip2"]
      ssl_offloaded                   = ssh.value["ssl_offloaded"]
      stream_based_uncompressed_limit = ssh.value["stream_based_uncompressed_limit"]
      tcp_window_maximum              = ssh.value["tcp_window_maximum"]
      tcp_window_minimum              = ssh.value["tcp_window_minimum"]
      tcp_window_size                 = ssh.value["tcp_window_size"]
      tcp_window_type                 = ssh.value["tcp_window_type"]
      uncompressed_nest_limit         = ssh.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit     = ssh.value["uncompressed_oversize_limit"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "feature_set" {
  description = "returns a string"
  value       = fortios_firewall_profileprotocoloptions.this.feature_set
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_profileprotocoloptions.this.id
}

output "oversize_log" {
  description = "returns a string"
  value       = fortios_firewall_profileprotocoloptions.this.oversize_log
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_firewall_profileprotocoloptions.this.replacemsg_group
}

output "rpc_over_http" {
  description = "returns a string"
  value       = fortios_firewall_profileprotocoloptions.this.rpc_over_http
}

output "switching_protocols_log" {
  description = "returns a string"
  value       = fortios_firewall_profileprotocoloptions.this.switching_protocols_log
}

output "this" {
  value = fortios_firewall_profileprotocoloptions.this
}
```

[top](#index)