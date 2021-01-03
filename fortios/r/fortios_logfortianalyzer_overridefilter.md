# fortios_logfortianalyzer_overridefilter

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
module "fortios_logfortianalyzer_overridefilter" {
  source = "./modules/fortios/r/fortios_logfortianalyzer_overridefilter"

  # anomaly - (optional) is a type of string
  anomaly = null
  # dlp_archive - (optional) is a type of string
  dlp_archive = null
  # dns - (optional) is a type of string
  dns = null
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
  # netscan_discovery - (optional) is a type of string
  netscan_discovery = null
  # netscan_vulnerability - (optional) is a type of string
  netscan_vulnerability = null
  # severity - (optional) is a type of string
  severity = null
  # sniffer_traffic - (optional) is a type of string
  sniffer_traffic = null
  # ssh - (optional) is a type of string
  ssh = null
  # voip - (optional) is a type of string
  voip = null
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

variable "dns" {
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

variable "netscan_discovery" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netscan_vulnerability" {
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

variable "ssh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voip" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortianalyzer_overridefilter" "this" {
  anomaly               = var.anomaly
  dlp_archive           = var.dlp_archive
  dns                   = var.dns
  filter                = var.filter
  filter_type           = var.filter_type
  forward_traffic       = var.forward_traffic
  gtp                   = var.gtp
  local_traffic         = var.local_traffic
  multicast_traffic     = var.multicast_traffic
  netscan_discovery     = var.netscan_discovery
  netscan_vulnerability = var.netscan_vulnerability
  severity              = var.severity
  sniffer_traffic       = var.sniffer_traffic
  ssh                   = var.ssh
  voip                  = var.voip
}
```

[top](#index)

### Outputs

```terraform
output "anomaly" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.anomaly
}

output "dlp_archive" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.dlp_archive
}

output "dns" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.dns
}

output "filter" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.filter
}

output "filter_type" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.filter_type
}

output "forward_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.forward_traffic
}

output "gtp" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.gtp
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.id
}

output "local_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.local_traffic
}

output "multicast_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.multicast_traffic
}

output "netscan_discovery" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.netscan_discovery
}

output "netscan_vulnerability" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.netscan_vulnerability
}

output "severity" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.severity
}

output "sniffer_traffic" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.sniffer_traffic
}

output "ssh" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.ssh
}

output "voip" {
  description = "returns a string"
  value       = fortios_logfortianalyzer_overridefilter.this.voip
}

output "this" {
  value = fortios_logfortianalyzer_overridefilter.this
}
```

[top](#index)