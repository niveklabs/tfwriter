# fortios_logfortiguard_setting

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
module "fortios_logfortiguard_setting" {
  source = "./modules/fortios/r/fortios_logfortiguard_setting"

  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # status - (optional) is a type of string
  status = null
  # upload_day - (optional) is a type of string
  upload_day = null
  # upload_interval - (optional) is a type of string
  upload_interval = null
  # upload_option - (optional) is a type of string
  upload_option = null
  # upload_time - (optional) is a type of string
  upload_time = null
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

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortiguard_setting" "this" {
  enc_algorithm         = var.enc_algorithm
  source_ip             = var.source_ip
  ssl_min_proto_version = var.ssl_min_proto_version
  status                = var.status
  upload_day            = var.upload_day
  upload_interval       = var.upload_interval
  upload_option         = var.upload_option
  upload_time           = var.upload_time
}
```

[top](#index)

### Outputs

```terraform
output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.enc_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.ssl_min_proto_version
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.status
}

output "upload_day" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_day
}

output "upload_interval" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_interval
}

output "upload_option" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_option
}

output "upload_time" {
  description = "returns a string"
  value       = fortios_logfortiguard_setting.this.upload_time
}

output "this" {
  value = fortios_logfortiguard_setting.this
}
```

[top](#index)