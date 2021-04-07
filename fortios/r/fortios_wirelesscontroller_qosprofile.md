# fortios_wirelesscontroller_qosprofile

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
module "fortios_wirelesscontroller_qosprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_qosprofile"

  # bandwidth_admission_control - (optional) is a type of string
  bandwidth_admission_control = null
  # bandwidth_capacity - (optional) is a type of number
  bandwidth_capacity = null
  # burst - (optional) is a type of string
  burst = null
  # call_admission_control - (optional) is a type of string
  call_admission_control = null
  # call_capacity - (optional) is a type of number
  call_capacity = null
  # comment - (optional) is a type of string
  comment = null
  # downlink - (optional) is a type of number
  downlink = null
  # downlink_sta - (optional) is a type of number
  downlink_sta = null
  # dscp_wmm_mapping - (optional) is a type of string
  dscp_wmm_mapping = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # uplink - (optional) is a type of number
  uplink = null
  # uplink_sta - (optional) is a type of number
  uplink_sta = null
  # wmm - (optional) is a type of string
  wmm = null
  # wmm_be_dscp - (optional) is a type of number
  wmm_be_dscp = null
  # wmm_bk_dscp - (optional) is a type of number
  wmm_bk_dscp = null
  # wmm_dscp_marking - (optional) is a type of string
  wmm_dscp_marking = null
  # wmm_uapsd - (optional) is a type of string
  wmm_uapsd = null
  # wmm_vi_dscp - (optional) is a type of number
  wmm_vi_dscp = null
  # wmm_vo_dscp - (optional) is a type of number
  wmm_vo_dscp = null

  dscp_wmm_be = [{
    id = null
  }]

  dscp_wmm_bk = [{
    id = null
  }]

  dscp_wmm_vi = [{
    id = null
  }]

  dscp_wmm_vo = [{
    id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_admission_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bandwidth_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "burst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "call_admission_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "call_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "downlink" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "downlink_sta" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dscp_wmm_mapping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uplink" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uplink_sta" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wmm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wmm_be_dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wmm_bk_dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wmm_dscp_marking" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wmm_uapsd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wmm_vi_dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wmm_vo_dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dscp_wmm_be" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "dscp_wmm_bk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "dscp_wmm_vi" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "dscp_wmm_vo" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_qosprofile" "this" {
  # bandwidth_admission_control - (optional) is a type of string
  bandwidth_admission_control = var.bandwidth_admission_control
  # bandwidth_capacity - (optional) is a type of number
  bandwidth_capacity = var.bandwidth_capacity
  # burst - (optional) is a type of string
  burst = var.burst
  # call_admission_control - (optional) is a type of string
  call_admission_control = var.call_admission_control
  # call_capacity - (optional) is a type of number
  call_capacity = var.call_capacity
  # comment - (optional) is a type of string
  comment = var.comment
  # downlink - (optional) is a type of number
  downlink = var.downlink
  # downlink_sta - (optional) is a type of number
  downlink_sta = var.downlink_sta
  # dscp_wmm_mapping - (optional) is a type of string
  dscp_wmm_mapping = var.dscp_wmm_mapping
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # uplink - (optional) is a type of number
  uplink = var.uplink
  # uplink_sta - (optional) is a type of number
  uplink_sta = var.uplink_sta
  # wmm - (optional) is a type of string
  wmm = var.wmm
  # wmm_be_dscp - (optional) is a type of number
  wmm_be_dscp = var.wmm_be_dscp
  # wmm_bk_dscp - (optional) is a type of number
  wmm_bk_dscp = var.wmm_bk_dscp
  # wmm_dscp_marking - (optional) is a type of string
  wmm_dscp_marking = var.wmm_dscp_marking
  # wmm_uapsd - (optional) is a type of string
  wmm_uapsd = var.wmm_uapsd
  # wmm_vi_dscp - (optional) is a type of number
  wmm_vi_dscp = var.wmm_vi_dscp
  # wmm_vo_dscp - (optional) is a type of number
  wmm_vo_dscp = var.wmm_vo_dscp

  dynamic "dscp_wmm_be" {
    for_each = var.dscp_wmm_be
    content {
      # id - (optional) is a type of number
      id = dscp_wmm_be.value["id"]
    }
  }

  dynamic "dscp_wmm_bk" {
    for_each = var.dscp_wmm_bk
    content {
      # id - (optional) is a type of number
      id = dscp_wmm_bk.value["id"]
    }
  }

  dynamic "dscp_wmm_vi" {
    for_each = var.dscp_wmm_vi
    content {
      # id - (optional) is a type of number
      id = dscp_wmm_vi.value["id"]
    }
  }

  dynamic "dscp_wmm_vo" {
    for_each = var.dscp_wmm_vo
    content {
      # id - (optional) is a type of number
      id = dscp_wmm_vo.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_admission_control" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.bandwidth_admission_control
}

output "bandwidth_capacity" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.bandwidth_capacity
}

output "burst" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.burst
}

output "call_admission_control" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.call_admission_control
}

output "call_capacity" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.call_capacity
}

output "comment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.comment
}

output "downlink" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.downlink
}

output "downlink_sta" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.downlink_sta
}

output "dscp_wmm_mapping" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.dscp_wmm_mapping
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.name
}

output "uplink" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.uplink
}

output "uplink_sta" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.uplink_sta
}

output "wmm" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm
}

output "wmm_be_dscp" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm_be_dscp
}

output "wmm_bk_dscp" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm_bk_dscp
}

output "wmm_dscp_marking" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm_dscp_marking
}

output "wmm_uapsd" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm_uapsd
}

output "wmm_vi_dscp" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm_vi_dscp
}

output "wmm_vo_dscp" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_qosprofile.this.wmm_vo_dscp
}

output "this" {
  value = fortios_wirelesscontroller_qosprofile.this
}
```

[top](#index)