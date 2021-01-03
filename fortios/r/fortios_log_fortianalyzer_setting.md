# fortios_log_fortianalyzer_setting

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
module "fortios_log_fortianalyzer_setting" {
  source = "./modules/fortios/r/fortios_log_fortianalyzer_setting"

  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # hmac_algorithm - (optional) is a type of string
  hmac_algorithm = null
  # reliable - (optional) is a type of string
  reliable = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # status - (required) is a type of string
  status = null
  # upload_option - (optional) is a type of string
  upload_option = null
}
```

[top](#index)

### Variables

```terraform
variable "enc_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hmac_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reliable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "upload_option" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_fortianalyzer_setting" "this" {
  enc_algorithm  = var.enc_algorithm
  hmac_algorithm = var.hmac_algorithm
  reliable       = var.reliable
  server         = var.server
  source_ip      = var.source_ip
  status         = var.status
  upload_option  = var.upload_option
}
```

[top](#index)

### Outputs

```terraform
output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.enc_algorithm
}

output "hmac_algorithm" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.hmac_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.id
}

output "reliable" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.reliable
}

output "server" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.source_ip
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_log_fortianalyzer_setting.this.upload_option
}

output "this" {
  value = fortios_log_fortianalyzer_setting.this
}
```

[top](#index)