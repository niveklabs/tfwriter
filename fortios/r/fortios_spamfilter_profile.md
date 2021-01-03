# fortios_spamfilter_profile

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
module "fortios_spamfilter_profile" {
  source = "./modules/fortios/r/fortios_spamfilter_profile"

  # comment - (optional) is a type of string
  comment = null
  # external - (optional) is a type of string
  external = null
  # flow_based - (optional) is a type of string
  flow_based = null
  # name - (required) is a type of string
  name = null
  # options - (optional) is a type of string
  options = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # spam_bwl_table - (optional) is a type of number
  spam_bwl_table = null
  # spam_bword_table - (optional) is a type of number
  spam_bword_table = null
  # spam_bword_threshold - (optional) is a type of number
  spam_bword_threshold = null
  # spam_filtering - (optional) is a type of string
  spam_filtering = null
  # spam_iptrust_table - (optional) is a type of number
  spam_iptrust_table = null
  # spam_log - (optional) is a type of string
  spam_log = null
  # spam_log_fortiguard_response - (optional) is a type of string
  spam_log_fortiguard_response = null
  # spam_mheader_table - (optional) is a type of number
  spam_mheader_table = null
  # spam_rbl_table - (optional) is a type of number
  spam_rbl_table = null

  gmail = [{
    log = null
  }]

  imap = [{
    action   = null
    log      = null
    tag_msg  = null
    tag_type = null
  }]

  mapi = [{
    action = null
    log    = null
  }]

  msn_hotmail = [{
    log = null
  }]

  pop3 = [{
    action   = null
    log      = null
    tag_msg  = null
    tag_type = null
  }]

  smtp = [{
    action         = null
    hdrip          = null
    local_override = null
    log            = null
    tag_msg        = null
    tag_type       = null
  }]

  yahoo_mail = [{
    log = null
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

variable "external" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_based" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spam_bwl_table" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spam_bword_table" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spam_bword_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spam_filtering" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spam_iptrust_table" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spam_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spam_log_fortiguard_response" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spam_mheader_table" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spam_rbl_table" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gmail" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log = string
    }
  ))
  default = []
}

variable "imap" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action   = string
      log      = string
      tag_msg  = string
      tag_type = string
    }
  ))
  default = []
}

variable "mapi" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action = string
      log    = string
    }
  ))
  default = []
}

variable "msn_hotmail" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log = string
    }
  ))
  default = []
}

variable "pop3" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action   = string
      log      = string
      tag_msg  = string
      tag_type = string
    }
  ))
  default = []
}

variable "smtp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action         = string
      hdrip          = string
      local_override = string
      log            = string
      tag_msg        = string
      tag_type       = string
    }
  ))
  default = []
}

variable "yahoo_mail" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_spamfilter_profile" "this" {
  comment                      = var.comment
  external                     = var.external
  flow_based                   = var.flow_based
  name                         = var.name
  options                      = var.options
  replacemsg_group             = var.replacemsg_group
  spam_bwl_table               = var.spam_bwl_table
  spam_bword_table             = var.spam_bword_table
  spam_bword_threshold         = var.spam_bword_threshold
  spam_filtering               = var.spam_filtering
  spam_iptrust_table           = var.spam_iptrust_table
  spam_log                     = var.spam_log
  spam_log_fortiguard_response = var.spam_log_fortiguard_response
  spam_mheader_table           = var.spam_mheader_table
  spam_rbl_table               = var.spam_rbl_table

  dynamic "gmail" {
    for_each = var.gmail
    content {
      log = gmail.value["log"]
    }
  }

  dynamic "imap" {
    for_each = var.imap
    content {
      action   = imap.value["action"]
      log      = imap.value["log"]
      tag_msg  = imap.value["tag_msg"]
      tag_type = imap.value["tag_type"]
    }
  }

  dynamic "mapi" {
    for_each = var.mapi
    content {
      action = mapi.value["action"]
      log    = mapi.value["log"]
    }
  }

  dynamic "msn_hotmail" {
    for_each = var.msn_hotmail
    content {
      log = msn_hotmail.value["log"]
    }
  }

  dynamic "pop3" {
    for_each = var.pop3
    content {
      action   = pop3.value["action"]
      log      = pop3.value["log"]
      tag_msg  = pop3.value["tag_msg"]
      tag_type = pop3.value["tag_type"]
    }
  }

  dynamic "smtp" {
    for_each = var.smtp
    content {
      action         = smtp.value["action"]
      hdrip          = smtp.value["hdrip"]
      local_override = smtp.value["local_override"]
      log            = smtp.value["log"]
      tag_msg        = smtp.value["tag_msg"]
      tag_type       = smtp.value["tag_type"]
    }
  }

  dynamic "yahoo_mail" {
    for_each = var.yahoo_mail
    content {
      log = yahoo_mail.value["log"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "external" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.external
}

output "flow_based" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.flow_based
}

output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.id
}

output "options" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.options
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.replacemsg_group
}

output "spam_bwl_table" {
  description = "returns a number"
  value       = fortios_spamfilter_profile.this.spam_bwl_table
}

output "spam_bword_table" {
  description = "returns a number"
  value       = fortios_spamfilter_profile.this.spam_bword_table
}

output "spam_bword_threshold" {
  description = "returns a number"
  value       = fortios_spamfilter_profile.this.spam_bword_threshold
}

output "spam_filtering" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.spam_filtering
}

output "spam_iptrust_table" {
  description = "returns a number"
  value       = fortios_spamfilter_profile.this.spam_iptrust_table
}

output "spam_log" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.spam_log
}

output "spam_log_fortiguard_response" {
  description = "returns a string"
  value       = fortios_spamfilter_profile.this.spam_log_fortiguard_response
}

output "spam_mheader_table" {
  description = "returns a number"
  value       = fortios_spamfilter_profile.this.spam_mheader_table
}

output "spam_rbl_table" {
  description = "returns a number"
  value       = fortios_spamfilter_profile.this.spam_rbl_table
}

output "this" {
  value = fortios_spamfilter_profile.this
}
```

[top](#index)