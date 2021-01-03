# panos_telemetry

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_telemetry" {
  source = "./modules/panos/r/panos_telemetry"

  # application_reports - (optional) is a type of bool
  application_reports = null
  # file_type_identification_reports - (optional) is a type of bool
  file_type_identification_reports = null
  # passive_dns_monitoring - (optional) is a type of bool
  passive_dns_monitoring = null
  # product_usage_stats - (optional) is a type of bool
  product_usage_stats = null
  # threat_prevention_data - (optional) is a type of bool
  threat_prevention_data = null
  # threat_prevention_packet_captures - (optional) is a type of bool
  threat_prevention_packet_captures = null
  # threat_prevention_reports - (optional) is a type of bool
  threat_prevention_reports = null
  # url_reports - (optional) is a type of bool
  url_reports = null
}
```

[top](#index)

### Variables

```terraform
variable "application_reports" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "file_type_identification_reports" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "passive_dns_monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "product_usage_stats" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "threat_prevention_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "threat_prevention_packet_captures" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "threat_prevention_reports" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "url_reports" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_telemetry" "this" {
  application_reports               = var.application_reports
  file_type_identification_reports  = var.file_type_identification_reports
  passive_dns_monitoring            = var.passive_dns_monitoring
  product_usage_stats               = var.product_usage_stats
  threat_prevention_data            = var.threat_prevention_data
  threat_prevention_packet_captures = var.threat_prevention_packet_captures
  threat_prevention_reports         = var.threat_prevention_reports
  url_reports                       = var.url_reports
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_telemetry.this.id
}

output "this" {
  value = panos_telemetry.this
}
```

[top](#index)