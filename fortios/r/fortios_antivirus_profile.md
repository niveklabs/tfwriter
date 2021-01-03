# fortios_antivirus_profile

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
module "fortios_antivirus_profile" {
  source = "./modules/fortios/r/fortios_antivirus_profile"

  # analytics_bl_filetype - (optional) is a type of number
  analytics_bl_filetype = null
  # analytics_db - (optional) is a type of string
  analytics_db = null
  # analytics_max_upload - (optional) is a type of number
  analytics_max_upload = null
  # analytics_wl_filetype - (optional) is a type of number
  analytics_wl_filetype = null
  # av_block_log - (optional) is a type of string
  av_block_log = null
  # av_virus_log - (optional) is a type of string
  av_virus_log = null
  # comment - (optional) is a type of string
  comment = null
  # extended_log - (optional) is a type of string
  extended_log = null
  # ftgd_analytics - (optional) is a type of string
  ftgd_analytics = null
  # inspection_mode - (optional) is a type of string
  inspection_mode = null
  # mobile_malware_db - (optional) is a type of string
  mobile_malware_db = null
  # name - (required) is a type of string
  name = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # scan_mode - (optional) is a type of string
  scan_mode = null

  content_disarm = [{
    cover_page                = null
    detect_only               = null
    office_embed              = null
    office_hylink             = null
    office_linked             = null
    office_macro              = null
    original_file_destination = null
    pdf_act_form              = null
    pdf_act_gotor             = null
    pdf_act_java              = null
    pdf_act_launch            = null
    pdf_act_movie             = null
    pdf_act_sound             = null
    pdf_embedfile             = null
    pdf_hyperlink             = null
    pdf_javacode              = null
  }]

  ftp = [{
    archive_block       = null
    archive_log         = null
    emulator            = null
    options             = null
    outbreak_prevention = null
  }]

  http = [{
    archive_block       = null
    archive_log         = null
    content_disarm      = null
    emulator            = null
    options             = null
    outbreak_prevention = null
  }]

  imap = [{
    archive_block       = null
    archive_log         = null
    content_disarm      = null
    emulator            = null
    executables         = null
    options             = null
    outbreak_prevention = null
  }]

  mapi = [{
    archive_block       = null
    archive_log         = null
    emulator            = null
    executables         = null
    options             = null
    outbreak_prevention = null
  }]

  nac_quar = [{
    expiry   = null
    infected = null
    log      = null
  }]

  nntp = [{
    archive_block       = null
    archive_log         = null
    emulator            = null
    options             = null
    outbreak_prevention = null
  }]

  outbreak_prevention = [{
    external_blocklist = null
    ftgd_service       = null
  }]

  pop3 = [{
    archive_block       = null
    archive_log         = null
    content_disarm      = null
    emulator            = null
    executables         = null
    options             = null
    outbreak_prevention = null
  }]

  smb = [{
    archive_block       = null
    archive_log         = null
    emulator            = null
    options             = null
    outbreak_prevention = null
  }]

  smtp = [{
    archive_block       = null
    archive_log         = null
    content_disarm      = null
    emulator            = null
    executables         = null
    options             = null
    outbreak_prevention = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "analytics_bl_filetype" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "analytics_db" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "analytics_max_upload" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "analytics_wl_filetype" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "av_block_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_virus_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftgd_analytics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mobile_malware_db" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_disarm" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cover_page                = string
      detect_only               = string
      office_embed              = string
      office_hylink             = string
      office_linked             = string
      office_macro              = string
      original_file_destination = string
      pdf_act_form              = string
      pdf_act_gotor             = string
      pdf_act_java              = string
      pdf_act_launch            = string
      pdf_act_movie             = string
      pdf_act_sound             = string
      pdf_embedfile             = string
      pdf_hyperlink             = string
      pdf_javacode              = string
    }
  ))
  default = []
}

variable "ftp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      emulator            = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      content_disarm      = string
      emulator            = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "imap" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      content_disarm      = string
      emulator            = string
      executables         = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "mapi" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      emulator            = string
      executables         = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "nac_quar" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      expiry   = string
      infected = string
      log      = string
    }
  ))
  default = []
}

variable "nntp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      emulator            = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "outbreak_prevention" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      external_blocklist = string
      ftgd_service       = string
    }
  ))
  default = []
}

variable "pop3" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      content_disarm      = string
      emulator            = string
      executables         = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "smb" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      emulator            = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}

variable "smtp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      archive_block       = string
      archive_log         = string
      content_disarm      = string
      emulator            = string
      executables         = string
      options             = string
      outbreak_prevention = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_antivirus_profile" "this" {
  analytics_bl_filetype = var.analytics_bl_filetype
  analytics_db          = var.analytics_db
  analytics_max_upload  = var.analytics_max_upload
  analytics_wl_filetype = var.analytics_wl_filetype
  av_block_log          = var.av_block_log
  av_virus_log          = var.av_virus_log
  comment               = var.comment
  extended_log          = var.extended_log
  ftgd_analytics        = var.ftgd_analytics
  inspection_mode       = var.inspection_mode
  mobile_malware_db     = var.mobile_malware_db
  name                  = var.name
  replacemsg_group      = var.replacemsg_group
  scan_mode             = var.scan_mode

  dynamic "content_disarm" {
    for_each = var.content_disarm
    content {
      cover_page                = content_disarm.value["cover_page"]
      detect_only               = content_disarm.value["detect_only"]
      office_embed              = content_disarm.value["office_embed"]
      office_hylink             = content_disarm.value["office_hylink"]
      office_linked             = content_disarm.value["office_linked"]
      office_macro              = content_disarm.value["office_macro"]
      original_file_destination = content_disarm.value["original_file_destination"]
      pdf_act_form              = content_disarm.value["pdf_act_form"]
      pdf_act_gotor             = content_disarm.value["pdf_act_gotor"]
      pdf_act_java              = content_disarm.value["pdf_act_java"]
      pdf_act_launch            = content_disarm.value["pdf_act_launch"]
      pdf_act_movie             = content_disarm.value["pdf_act_movie"]
      pdf_act_sound             = content_disarm.value["pdf_act_sound"]
      pdf_embedfile             = content_disarm.value["pdf_embedfile"]
      pdf_hyperlink             = content_disarm.value["pdf_hyperlink"]
      pdf_javacode              = content_disarm.value["pdf_javacode"]
    }
  }

  dynamic "ftp" {
    for_each = var.ftp
    content {
      archive_block       = ftp.value["archive_block"]
      archive_log         = ftp.value["archive_log"]
      emulator            = ftp.value["emulator"]
      options             = ftp.value["options"]
      outbreak_prevention = ftp.value["outbreak_prevention"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      archive_block       = http.value["archive_block"]
      archive_log         = http.value["archive_log"]
      content_disarm      = http.value["content_disarm"]
      emulator            = http.value["emulator"]
      options             = http.value["options"]
      outbreak_prevention = http.value["outbreak_prevention"]
    }
  }

  dynamic "imap" {
    for_each = var.imap
    content {
      archive_block       = imap.value["archive_block"]
      archive_log         = imap.value["archive_log"]
      content_disarm      = imap.value["content_disarm"]
      emulator            = imap.value["emulator"]
      executables         = imap.value["executables"]
      options             = imap.value["options"]
      outbreak_prevention = imap.value["outbreak_prevention"]
    }
  }

  dynamic "mapi" {
    for_each = var.mapi
    content {
      archive_block       = mapi.value["archive_block"]
      archive_log         = mapi.value["archive_log"]
      emulator            = mapi.value["emulator"]
      executables         = mapi.value["executables"]
      options             = mapi.value["options"]
      outbreak_prevention = mapi.value["outbreak_prevention"]
    }
  }

  dynamic "nac_quar" {
    for_each = var.nac_quar
    content {
      expiry   = nac_quar.value["expiry"]
      infected = nac_quar.value["infected"]
      log      = nac_quar.value["log"]
    }
  }

  dynamic "nntp" {
    for_each = var.nntp
    content {
      archive_block       = nntp.value["archive_block"]
      archive_log         = nntp.value["archive_log"]
      emulator            = nntp.value["emulator"]
      options             = nntp.value["options"]
      outbreak_prevention = nntp.value["outbreak_prevention"]
    }
  }

  dynamic "outbreak_prevention" {
    for_each = var.outbreak_prevention
    content {
      external_blocklist = outbreak_prevention.value["external_blocklist"]
      ftgd_service       = outbreak_prevention.value["ftgd_service"]
    }
  }

  dynamic "pop3" {
    for_each = var.pop3
    content {
      archive_block       = pop3.value["archive_block"]
      archive_log         = pop3.value["archive_log"]
      content_disarm      = pop3.value["content_disarm"]
      emulator            = pop3.value["emulator"]
      executables         = pop3.value["executables"]
      options             = pop3.value["options"]
      outbreak_prevention = pop3.value["outbreak_prevention"]
    }
  }

  dynamic "smb" {
    for_each = var.smb
    content {
      archive_block       = smb.value["archive_block"]
      archive_log         = smb.value["archive_log"]
      emulator            = smb.value["emulator"]
      options             = smb.value["options"]
      outbreak_prevention = smb.value["outbreak_prevention"]
    }
  }

  dynamic "smtp" {
    for_each = var.smtp
    content {
      archive_block       = smtp.value["archive_block"]
      archive_log         = smtp.value["archive_log"]
      content_disarm      = smtp.value["content_disarm"]
      emulator            = smtp.value["emulator"]
      executables         = smtp.value["executables"]
      options             = smtp.value["options"]
      outbreak_prevention = smtp.value["outbreak_prevention"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "analytics_bl_filetype" {
  description = "returns a number"
  value       = fortios_antivirus_profile.this.analytics_bl_filetype
}

output "analytics_db" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.analytics_db
}

output "analytics_max_upload" {
  description = "returns a number"
  value       = fortios_antivirus_profile.this.analytics_max_upload
}

output "analytics_wl_filetype" {
  description = "returns a number"
  value       = fortios_antivirus_profile.this.analytics_wl_filetype
}

output "av_block_log" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.av_block_log
}

output "av_virus_log" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.av_virus_log
}

output "extended_log" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.extended_log
}

output "ftgd_analytics" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.ftgd_analytics
}

output "id" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.id
}

output "inspection_mode" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.inspection_mode
}

output "mobile_malware_db" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.mobile_malware_db
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.replacemsg_group
}

output "scan_mode" {
  description = "returns a string"
  value       = fortios_antivirus_profile.this.scan_mode
}

output "this" {
  value = fortios_antivirus_profile.this
}
```

[top](#index)