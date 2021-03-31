# fortios_emailfilter_profile

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
module "fortios_emailfilter_profile" {
  source = "./modules/fortios/r/fortios_emailfilter_profile"

  # comment - (optional) is a type of string
  comment = null
  # external - (optional) is a type of string
  external = null
  # feature_set - (optional) is a type of string
  feature_set = null
  # name - (optional) is a type of string
  name = null
  # options - (optional) is a type of string
  options = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # spam_bal_table - (optional) is a type of number
  spam_bal_table = null
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

  file_filter = [{
    entries = [{
      action  = null
      comment = null
      file_type = [{
        name = null
      }]
      filter             = null
      password_protected = null
      protocol           = null
    }]
    log                   = null
    scan_archive_contents = null
    status                = null
  }]

  gmail = [{
    log     = null
    log_all = null
  }]

  imap = [{
    action   = null
    log      = null
    log_all  = null
    tag_msg  = null
    tag_type = null
  }]

  mapi = [{
    action  = null
    log     = null
    log_all = null
  }]

  msn_hotmail = [{
    log     = null
    log_all = null
  }]

  other_webmails = [{
    log_all = null
  }]

  pop3 = [{
    action   = null
    log      = null
    log_all  = null
    tag_msg  = null
    tag_type = null
  }]

  smtp = [{
    action         = null
    hdrip          = null
    local_override = null
    log            = null
    log_all        = null
    tag_msg        = null
    tag_type       = null
  }]

  yahoo_mail = [{
    log     = null
    log_all = null
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

variable "feature_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "spam_bal_table" {
  description = "(optional)"
  type        = number
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

variable "file_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      entries = list(object(
        {
          action  = string
          comment = string
          file_type = list(object(
            {
              name = string
            }
          ))
          filter             = string
          password_protected = string
          protocol           = string
        }
      ))
      log                   = string
      scan_archive_contents = string
      status                = string
    }
  ))
  default = []
}

variable "gmail" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log     = string
      log_all = string
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
      log_all  = string
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
      action  = string
      log     = string
      log_all = string
    }
  ))
  default = []
}

variable "msn_hotmail" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log     = string
      log_all = string
    }
  ))
  default = []
}

variable "other_webmails" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log_all = string
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
      log_all  = string
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
      log_all        = string
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
      log     = string
      log_all = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_emailfilter_profile" "this" {
  comment                      = var.comment
  external                     = var.external
  feature_set                  = var.feature_set
  name                         = var.name
  options                      = var.options
  replacemsg_group             = var.replacemsg_group
  spam_bal_table               = var.spam_bal_table
  spam_bwl_table               = var.spam_bwl_table
  spam_bword_table             = var.spam_bword_table
  spam_bword_threshold         = var.spam_bword_threshold
  spam_filtering               = var.spam_filtering
  spam_iptrust_table           = var.spam_iptrust_table
  spam_log                     = var.spam_log
  spam_log_fortiguard_response = var.spam_log_fortiguard_response
  spam_mheader_table           = var.spam_mheader_table
  spam_rbl_table               = var.spam_rbl_table

  dynamic "file_filter" {
    for_each = var.file_filter
    content {
      log                   = file_filter.value["log"]
      scan_archive_contents = file_filter.value["scan_archive_contents"]
      status                = file_filter.value["status"]

      dynamic "entries" {
        for_each = file_filter.value.entries
        content {
          action             = entries.value["action"]
          comment            = entries.value["comment"]
          filter             = entries.value["filter"]
          password_protected = entries.value["password_protected"]
          protocol           = entries.value["protocol"]

          dynamic "file_type" {
            for_each = entries.value.file_type
            content {
              name = file_type.value["name"]
            }
          }

        }
      }

    }
  }

  dynamic "gmail" {
    for_each = var.gmail
    content {
      log     = gmail.value["log"]
      log_all = gmail.value["log_all"]
    }
  }

  dynamic "imap" {
    for_each = var.imap
    content {
      action   = imap.value["action"]
      log      = imap.value["log"]
      log_all  = imap.value["log_all"]
      tag_msg  = imap.value["tag_msg"]
      tag_type = imap.value["tag_type"]
    }
  }

  dynamic "mapi" {
    for_each = var.mapi
    content {
      action  = mapi.value["action"]
      log     = mapi.value["log"]
      log_all = mapi.value["log_all"]
    }
  }

  dynamic "msn_hotmail" {
    for_each = var.msn_hotmail
    content {
      log     = msn_hotmail.value["log"]
      log_all = msn_hotmail.value["log_all"]
    }
  }

  dynamic "other_webmails" {
    for_each = var.other_webmails
    content {
      log_all = other_webmails.value["log_all"]
    }
  }

  dynamic "pop3" {
    for_each = var.pop3
    content {
      action   = pop3.value["action"]
      log      = pop3.value["log"]
      log_all  = pop3.value["log_all"]
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
      log_all        = smtp.value["log_all"]
      tag_msg        = smtp.value["tag_msg"]
      tag_type       = smtp.value["tag_type"]
    }
  }

  dynamic "yahoo_mail" {
    for_each = var.yahoo_mail
    content {
      log     = yahoo_mail.value["log"]
      log_all = yahoo_mail.value["log_all"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "external" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.external
}

output "feature_set" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.feature_set
}

output "id" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.name
}

output "options" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.options
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.replacemsg_group
}

output "spam_bal_table" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_bal_table
}

output "spam_bwl_table" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_bwl_table
}

output "spam_bword_table" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_bword_table
}

output "spam_bword_threshold" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_bword_threshold
}

output "spam_filtering" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.spam_filtering
}

output "spam_iptrust_table" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_iptrust_table
}

output "spam_log" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.spam_log
}

output "spam_log_fortiguard_response" {
  description = "returns a string"
  value       = fortios_emailfilter_profile.this.spam_log_fortiguard_response
}

output "spam_mheader_table" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_mheader_table
}

output "spam_rbl_table" {
  description = "returns a number"
  value       = fortios_emailfilter_profile.this.spam_rbl_table
}

output "this" {
  value = fortios_emailfilter_profile.this
}
```

[top](#index)