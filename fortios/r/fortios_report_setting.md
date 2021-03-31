# fortios_report_setting

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
module "fortios_report_setting" {
  source = "./modules/fortios/r/fortios_report_setting"

  # fortiview - (optional) is a type of string
  fortiview = null
  # pdf_report - (optional) is a type of string
  pdf_report = null
  # report_source - (optional) is a type of string
  report_source = null
  # top_n - (optional) is a type of number
  top_n = null
  # web_browsing_threshold - (optional) is a type of number
  web_browsing_threshold = null
}
```

[top](#index)

### Variables

```terraform
variable "fortiview" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pdf_report" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "report_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "top_n" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "web_browsing_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_report_setting" "this" {
  fortiview              = var.fortiview
  pdf_report             = var.pdf_report
  report_source          = var.report_source
  top_n                  = var.top_n
  web_browsing_threshold = var.web_browsing_threshold
}
```

[top](#index)

### Outputs

```terraform
output "fortiview" {
  description = "returns a string"
  value       = fortios_report_setting.this.fortiview
}

output "id" {
  description = "returns a string"
  value       = fortios_report_setting.this.id
}

output "pdf_report" {
  description = "returns a string"
  value       = fortios_report_setting.this.pdf_report
}

output "report_source" {
  description = "returns a string"
  value       = fortios_report_setting.this.report_source
}

output "top_n" {
  description = "returns a number"
  value       = fortios_report_setting.this.top_n
}

output "web_browsing_threshold" {
  description = "returns a number"
  value       = fortios_report_setting.this.web_browsing_threshold
}

output "this" {
  value = fortios_report_setting.this
}
```

[top](#index)