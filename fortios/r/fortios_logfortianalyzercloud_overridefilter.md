# fortios_logfortianalyzercloud_overridefilter

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
module "fortios_logfortianalyzercloud_overridefilter" {
  source = "./modules/fortios/r/fortios_logfortianalyzercloud_overridefilter"

  # anomaly - (optional) is a type of string
  anomaly = null
  # dlp_archive - (optional) is a type of string
  dlp_archive = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # filter - (optional) is a type of string
  filter = null
  # filter_type - (optional) is a type of string
  filter_type = null
  # forward_traffic - (optional) is a type of string
  forward_traffic = null
  # gtp - (optional) is a type of string
  gtp = null
  # local_traffic - (optional) is a type of string
  local_traffic = null
  # multicast_traffic - (optional) is a type of string
  multicast_traffic = null
  # severity - (optional) is a type of string
  severity = null
  # sniffer_traffic - (optional) is a type of string
  sniffer_traffic = null
  # voip - (optional) is a type of string
  voip = null

  free_style = [{
    category    = null
    filter      = null
    filter_type = null
    id          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "anomaly" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dlp_archive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gtp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sniffer_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "free_style" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category    = string
      filter      = string
      filter_type = string
      id          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortianalyzercloud_overridefilter" "this" {
  anomaly               = var.anomaly
  dlp_archive           = var.dlp_archive
  dynamic_sort_subtable = var.dynamic_sort_subtable
  filter                = var.filter
  filter_type           = var.filter_type
  forward_traffic       = var.forward_traffic
  gtp                   = var.gtp
  local_traffic         = var.local_traffic
  multicast_traffic     = var.multicast_traffic
  severity              = var.severity
  sniffer_traffic       = var.sniffer_traffic
  voip                  = var.voip

  dynamic "free_style" {
    for_each = var.free_style
    content {
      category    = free_style.value["category"]
      filter      = free_style.value["filter"]
      filter_type = free_style.value["filter_type"]
      id          = free_style.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "anomaly" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.anomaly
}

output "dlp_archive" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.dlp_archive
}

output "filter" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.filter
}

output "filter_type" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.filter_type
}

output "forward_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.forward_traffic
}

output "gtp" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.gtp
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.id
}

output "local_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.local_traffic
}

output "multicast_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.multicast_traffic
}

output "severity" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.severity
}

output "sniffer_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.sniffer_traffic
}

output "voip" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridefilter.this.voip
}

output "this" {
  value = fortios_logfortianalyzercloud_overridefilter.this
}
```

[top](#index)