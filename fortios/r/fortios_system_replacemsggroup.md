# fortios_system_replacemsggroup

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
module "fortios_system_replacemsggroup" {
  source = "./modules/fortios/r/fortios_system_replacemsggroup"

  # comment - (optional) is a type of string
  comment = null
  # group_type - (required) is a type of string
  group_type = null
  # name - (optional) is a type of string
  name = null

  admin = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  alertmail = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  auth = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  custom_message = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  device_detection_portal = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  ec = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  fortiguard_wf = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  ftp = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  http = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  icap = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  mail = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  nac_quar = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  nntp = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  spam = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  sslvpn = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  traffic_quota = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  utm = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
  }]

  webproxy = [{
    buffer   = null
    format   = null
    header   = null
    msg_type = null
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

variable "group_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "alertmail" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "auth" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "custom_message" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "device_detection_portal" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "ec" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "fortiguard_wf" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "ftp" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "icap" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "mail" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "nac_quar" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "nntp" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "spam" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "sslvpn" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "traffic_quota" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "utm" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}

variable "webproxy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      buffer   = string
      format   = string
      header   = string
      msg_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_replacemsggroup" "this" {
  comment    = var.comment
  group_type = var.group_type
  name       = var.name

  dynamic "admin" {
    for_each = var.admin
    content {
      buffer   = admin.value["buffer"]
      format   = admin.value["format"]
      header   = admin.value["header"]
      msg_type = admin.value["msg_type"]
    }
  }

  dynamic "alertmail" {
    for_each = var.alertmail
    content {
      buffer   = alertmail.value["buffer"]
      format   = alertmail.value["format"]
      header   = alertmail.value["header"]
      msg_type = alertmail.value["msg_type"]
    }
  }

  dynamic "auth" {
    for_each = var.auth
    content {
      buffer   = auth.value["buffer"]
      format   = auth.value["format"]
      header   = auth.value["header"]
      msg_type = auth.value["msg_type"]
    }
  }

  dynamic "custom_message" {
    for_each = var.custom_message
    content {
      buffer   = custom_message.value["buffer"]
      format   = custom_message.value["format"]
      header   = custom_message.value["header"]
      msg_type = custom_message.value["msg_type"]
    }
  }

  dynamic "device_detection_portal" {
    for_each = var.device_detection_portal
    content {
      buffer   = device_detection_portal.value["buffer"]
      format   = device_detection_portal.value["format"]
      header   = device_detection_portal.value["header"]
      msg_type = device_detection_portal.value["msg_type"]
    }
  }

  dynamic "ec" {
    for_each = var.ec
    content {
      buffer   = ec.value["buffer"]
      format   = ec.value["format"]
      header   = ec.value["header"]
      msg_type = ec.value["msg_type"]
    }
  }

  dynamic "fortiguard_wf" {
    for_each = var.fortiguard_wf
    content {
      buffer   = fortiguard_wf.value["buffer"]
      format   = fortiguard_wf.value["format"]
      header   = fortiguard_wf.value["header"]
      msg_type = fortiguard_wf.value["msg_type"]
    }
  }

  dynamic "ftp" {
    for_each = var.ftp
    content {
      buffer   = ftp.value["buffer"]
      format   = ftp.value["format"]
      header   = ftp.value["header"]
      msg_type = ftp.value["msg_type"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      buffer   = http.value["buffer"]
      format   = http.value["format"]
      header   = http.value["header"]
      msg_type = http.value["msg_type"]
    }
  }

  dynamic "icap" {
    for_each = var.icap
    content {
      buffer   = icap.value["buffer"]
      format   = icap.value["format"]
      header   = icap.value["header"]
      msg_type = icap.value["msg_type"]
    }
  }

  dynamic "mail" {
    for_each = var.mail
    content {
      buffer   = mail.value["buffer"]
      format   = mail.value["format"]
      header   = mail.value["header"]
      msg_type = mail.value["msg_type"]
    }
  }

  dynamic "nac_quar" {
    for_each = var.nac_quar
    content {
      buffer   = nac_quar.value["buffer"]
      format   = nac_quar.value["format"]
      header   = nac_quar.value["header"]
      msg_type = nac_quar.value["msg_type"]
    }
  }

  dynamic "nntp" {
    for_each = var.nntp
    content {
      buffer   = nntp.value["buffer"]
      format   = nntp.value["format"]
      header   = nntp.value["header"]
      msg_type = nntp.value["msg_type"]
    }
  }

  dynamic "spam" {
    for_each = var.spam
    content {
      buffer   = spam.value["buffer"]
      format   = spam.value["format"]
      header   = spam.value["header"]
      msg_type = spam.value["msg_type"]
    }
  }

  dynamic "sslvpn" {
    for_each = var.sslvpn
    content {
      buffer   = sslvpn.value["buffer"]
      format   = sslvpn.value["format"]
      header   = sslvpn.value["header"]
      msg_type = sslvpn.value["msg_type"]
    }
  }

  dynamic "traffic_quota" {
    for_each = var.traffic_quota
    content {
      buffer   = traffic_quota.value["buffer"]
      format   = traffic_quota.value["format"]
      header   = traffic_quota.value["header"]
      msg_type = traffic_quota.value["msg_type"]
    }
  }

  dynamic "utm" {
    for_each = var.utm
    content {
      buffer   = utm.value["buffer"]
      format   = utm.value["format"]
      header   = utm.value["header"]
      msg_type = utm.value["msg_type"]
    }
  }

  dynamic "webproxy" {
    for_each = var.webproxy
    content {
      buffer   = webproxy.value["buffer"]
      format   = webproxy.value["format"]
      header   = webproxy.value["header"]
      msg_type = webproxy.value["msg_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_replacemsggroup.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_replacemsggroup.this.name
}

output "this" {
  value = fortios_system_replacemsggroup.this
}
```

[top](#index)