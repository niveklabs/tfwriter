# fortios_system_accprofile

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
module "fortios_system_accprofile" {
  source = "./modules/fortios/r/fortios_system_accprofile"

  # admintimeout - (optional) is a type of number
  admintimeout = null
  # admintimeout_override - (optional) is a type of string
  admintimeout_override = null
  # authgrp - (optional) is a type of string
  authgrp = null
  # comments - (optional) is a type of string
  comments = null
  # ftviewgrp - (optional) is a type of string
  ftviewgrp = null
  # fwgrp - (optional) is a type of string
  fwgrp = null
  # loggrp - (optional) is a type of string
  loggrp = null
  # name - (required) is a type of string
  name = null
  # netgrp - (optional) is a type of string
  netgrp = null
  # scope - (optional) is a type of string
  scope = null
  # secfabgrp - (optional) is a type of string
  secfabgrp = null
  # sysgrp - (optional) is a type of string
  sysgrp = null
  # system_diagnostics - (optional) is a type of string
  system_diagnostics = null
  # utmgrp - (optional) is a type of string
  utmgrp = null
  # vpngrp - (optional) is a type of string
  vpngrp = null
  # wanoptgrp - (optional) is a type of string
  wanoptgrp = null
  # wifi - (optional) is a type of string
  wifi = null

  fwgrp_permission = [{
    address  = null
    policy   = null
    schedule = null
    service  = null
  }]

  loggrp_permission = [{
    config        = null
    data_access   = null
    report_access = null
    threat_weight = null
  }]

  netgrp_permission = [{
    cfg            = null
    packet_capture = null
    route_cfg      = null
  }]

  sysgrp_permission = [{
    admin = null
    cfg   = null
    mnt   = null
    upd   = null
  }]

  utmgrp_permission = [{
    antivirus            = null
    application_control  = null
    data_loss_prevention = null
    dnsfilter            = null
    emailfilter          = null
    endpoint_control     = null
    file_filter          = null
    icap                 = null
    ips                  = null
    spamfilter           = null
    voip                 = null
    waf                  = null
    webfilter            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admintimeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admintimeout_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftviewgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fwgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "loggrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "netgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secfabgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sysgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_diagnostics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "utmgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpngrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanoptgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wifi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fwgrp_permission" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address  = string
      policy   = string
      schedule = string
      service  = string
    }
  ))
  default = []
}

variable "loggrp_permission" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      config        = string
      data_access   = string
      report_access = string
      threat_weight = string
    }
  ))
  default = []
}

variable "netgrp_permission" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cfg            = string
      packet_capture = string
      route_cfg      = string
    }
  ))
  default = []
}

variable "sysgrp_permission" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin = string
      cfg   = string
      mnt   = string
      upd   = string
    }
  ))
  default = []
}

variable "utmgrp_permission" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      antivirus            = string
      application_control  = string
      data_loss_prevention = string
      dnsfilter            = string
      emailfilter          = string
      endpoint_control     = string
      file_filter          = string
      icap                 = string
      ips                  = string
      spamfilter           = string
      voip                 = string
      waf                  = string
      webfilter            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_accprofile" "this" {
  admintimeout          = var.admintimeout
  admintimeout_override = var.admintimeout_override
  authgrp               = var.authgrp
  comments              = var.comments
  ftviewgrp             = var.ftviewgrp
  fwgrp                 = var.fwgrp
  loggrp                = var.loggrp
  name                  = var.name
  netgrp                = var.netgrp
  scope                 = var.scope
  secfabgrp             = var.secfabgrp
  sysgrp                = var.sysgrp
  system_diagnostics    = var.system_diagnostics
  utmgrp                = var.utmgrp
  vpngrp                = var.vpngrp
  wanoptgrp             = var.wanoptgrp
  wifi                  = var.wifi

  dynamic "fwgrp_permission" {
    for_each = var.fwgrp_permission
    content {
      address  = fwgrp_permission.value["address"]
      policy   = fwgrp_permission.value["policy"]
      schedule = fwgrp_permission.value["schedule"]
      service  = fwgrp_permission.value["service"]
    }
  }

  dynamic "loggrp_permission" {
    for_each = var.loggrp_permission
    content {
      config        = loggrp_permission.value["config"]
      data_access   = loggrp_permission.value["data_access"]
      report_access = loggrp_permission.value["report_access"]
      threat_weight = loggrp_permission.value["threat_weight"]
    }
  }

  dynamic "netgrp_permission" {
    for_each = var.netgrp_permission
    content {
      cfg            = netgrp_permission.value["cfg"]
      packet_capture = netgrp_permission.value["packet_capture"]
      route_cfg      = netgrp_permission.value["route_cfg"]
    }
  }

  dynamic "sysgrp_permission" {
    for_each = var.sysgrp_permission
    content {
      admin = sysgrp_permission.value["admin"]
      cfg   = sysgrp_permission.value["cfg"]
      mnt   = sysgrp_permission.value["mnt"]
      upd   = sysgrp_permission.value["upd"]
    }
  }

  dynamic "utmgrp_permission" {
    for_each = var.utmgrp_permission
    content {
      antivirus            = utmgrp_permission.value["antivirus"]
      application_control  = utmgrp_permission.value["application_control"]
      data_loss_prevention = utmgrp_permission.value["data_loss_prevention"]
      dnsfilter            = utmgrp_permission.value["dnsfilter"]
      emailfilter          = utmgrp_permission.value["emailfilter"]
      endpoint_control     = utmgrp_permission.value["endpoint_control"]
      file_filter          = utmgrp_permission.value["file_filter"]
      icap                 = utmgrp_permission.value["icap"]
      ips                  = utmgrp_permission.value["ips"]
      spamfilter           = utmgrp_permission.value["spamfilter"]
      voip                 = utmgrp_permission.value["voip"]
      waf                  = utmgrp_permission.value["waf"]
      webfilter            = utmgrp_permission.value["webfilter"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admintimeout" {
  description = "returns a number"
  value       = fortios_system_accprofile.this.admintimeout
}

output "admintimeout_override" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.admintimeout_override
}

output "authgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.authgrp
}

output "ftviewgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.ftviewgrp
}

output "fwgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.fwgrp
}

output "id" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.id
}

output "loggrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.loggrp
}

output "netgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.netgrp
}

output "scope" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.scope
}

output "secfabgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.secfabgrp
}

output "sysgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.sysgrp
}

output "system_diagnostics" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.system_diagnostics
}

output "utmgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.utmgrp
}

output "vpngrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.vpngrp
}

output "wanoptgrp" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.wanoptgrp
}

output "wifi" {
  description = "returns a string"
  value       = fortios_system_accprofile.this.wifi
}

output "this" {
  value = fortios_system_accprofile.this
}
```

[top](#index)