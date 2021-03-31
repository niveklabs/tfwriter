# fortios_vpncertificate_ocspserver

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
module "fortios_vpncertificate_ocspserver" {
  source = "./modules/fortios/r/fortios_vpncertificate_ocspserver"

  # cert - (optional) is a type of string
  cert = null
  # name - (optional) is a type of string
  name = null
  # secondary_cert - (optional) is a type of string
  secondary_cert = null
  # secondary_url - (optional) is a type of string
  secondary_url = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # unavail_action - (optional) is a type of string
  unavail_action = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unavail_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpncertificate_ocspserver" "this" {
  cert           = var.cert
  name           = var.name
  secondary_cert = var.secondary_cert
  secondary_url  = var.secondary_url
  source_ip      = var.source_ip
  unavail_action = var.unavail_action
  url            = var.url
}
```

[top](#index)

### Outputs

```terraform
output "cert" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.cert
}

output "id" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.name
}

output "secondary_cert" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.secondary_cert
}

output "secondary_url" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.secondary_url
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.source_ip
}

output "unavail_action" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.unavail_action
}

output "url" {
  description = "returns a string"
  value       = fortios_vpncertificate_ocspserver.this.url
}

output "this" {
  value = fortios_vpncertificate_ocspserver.this
}
```

[top](#index)