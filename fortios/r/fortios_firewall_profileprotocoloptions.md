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
    fortios = ">= 1.6.18"
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

  dns = [{
    ports  = null
    status = null
  }]

  ftp = [{
    comfort_amount              = null
    comfort_interval            = null
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    scan_bzip2                  = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  http = [{
    block_page_status_code      = null
    comfort_amount              = null
    comfort_interval            = null
    fortinet_bar                = null
    fortinet_bar_port           = null
    http_policy                 = null
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    post_lang                   = null
    range_block                 = null
    retry_count                 = null
    scan_bzip2                  = null
    status                      = null
    streaming_content_bypass    = null
    strip_x_forwarded_for       = null
    switching_protocols         = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  imap = [{
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    scan_bzip2                  = null
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
    scan_bzip2                  = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
  }]

  smtp = [{
    inspect_all                 = null
    options                     = null
    oversize_limit              = null
    ports                       = null
    scan_bzip2                  = null
    server_busy                 = null
    status                      = null
    uncompressed_nest_limit     = null
    uncompressed_oversize_limit = null
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
      comfort_amount              = number
      comfort_interval            = number
      inspect_all                 = string
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

variable "http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      block_page_status_code      = number
      comfort_amount              = number
      comfort_interval            = number
      fortinet_bar                = string
      fortinet_bar_port           = number
      http_policy                 = string
      inspect_all                 = string
      options                     = string
      oversize_limit              = number
      ports                       = number
      post_lang                   = string
      range_block                 = string
      retry_count                 = number
      scan_bzip2                  = string
      status                      = string
      streaming_content_bypass    = string
      strip_x_forwarded_for       = string
      switching_protocols         = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
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
      scan_bzip2                  = string
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
      scan_bzip2                  = string
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
      scan_bzip2                  = string
      server_busy                 = string
      status                      = string
      uncompressed_nest_limit     = number
      uncompressed_oversize_limit = number
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
  name                    = var.name
  oversize_log            = var.oversize_log
  replacemsg_group        = var.replacemsg_group
  rpc_over_http           = var.rpc_over_http
  switching_protocols_log = var.switching_protocols_log

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
      comfort_amount              = ftp.value["comfort_amount"]
      comfort_interval            = ftp.value["comfort_interval"]
      inspect_all                 = ftp.value["inspect_all"]
      options                     = ftp.value["options"]
      oversize_limit              = ftp.value["oversize_limit"]
      ports                       = ftp.value["ports"]
      scan_bzip2                  = ftp.value["scan_bzip2"]
      status                      = ftp.value["status"]
      uncompressed_nest_limit     = ftp.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = ftp.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      block_page_status_code      = http.value["block_page_status_code"]
      comfort_amount              = http.value["comfort_amount"]
      comfort_interval            = http.value["comfort_interval"]
      fortinet_bar                = http.value["fortinet_bar"]
      fortinet_bar_port           = http.value["fortinet_bar_port"]
      http_policy                 = http.value["http_policy"]
      inspect_all                 = http.value["inspect_all"]
      options                     = http.value["options"]
      oversize_limit              = http.value["oversize_limit"]
      ports                       = http.value["ports"]
      post_lang                   = http.value["post_lang"]
      range_block                 = http.value["range_block"]
      retry_count                 = http.value["retry_count"]
      scan_bzip2                  = http.value["scan_bzip2"]
      status                      = http.value["status"]
      streaming_content_bypass    = http.value["streaming_content_bypass"]
      strip_x_forwarded_for       = http.value["strip_x_forwarded_for"]
      switching_protocols         = http.value["switching_protocols"]
      uncompressed_nest_limit     = http.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = http.value["uncompressed_oversize_limit"]
    }
  }

  dynamic "imap" {
    for_each = var.imap
    content {
      inspect_all                 = imap.value["inspect_all"]
      options                     = imap.value["options"]
      oversize_limit              = imap.value["oversize_limit"]
      ports                       = imap.value["ports"]
      scan_bzip2                  = imap.value["scan_bzip2"]
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
      scan_bzip2                  = pop3.value["scan_bzip2"]
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
      scan_bzip2                  = smtp.value["scan_bzip2"]
      server_busy                 = smtp.value["server_busy"]
      status                      = smtp.value["status"]
      uncompressed_nest_limit     = smtp.value["uncompressed_nest_limit"]
      uncompressed_oversize_limit = smtp.value["uncompressed_oversize_limit"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
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