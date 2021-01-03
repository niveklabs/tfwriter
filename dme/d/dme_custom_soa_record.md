# dme_custom_soa_record

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_custom_soa_record" {
  source = "./modules/dme/d/dme_custom_soa_record"

  # comp - (optional) is a type of string
  comp = null
  # email - (optional) is a type of string
  email = null
  # expire - (optional) is a type of string
  expire = null
  # name - (required) is a type of string
  name = null
  # negative_cache - (optional) is a type of string
  negative_cache = null
  # refresh - (optional) is a type of string
  refresh = null
  # retry - (optional) is a type of string
  retry = null
  # serial - (optional) is a type of string
  serial = null
  # ttl - (optional) is a type of string
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "comp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expire" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "negative_cache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refresh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retry" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "dme_custom_soa_record" "this" {
  comp           = var.comp
  email          = var.email
  expire         = var.expire
  name           = var.name
  negative_cache = var.negative_cache
  refresh        = var.refresh
  retry          = var.retry
  serial         = var.serial
  ttl            = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "comp" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.comp
}

output "email" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.email
}

output "expire" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.expire
}

output "id" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.id
}

output "negative_cache" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.negative_cache
}

output "refresh" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.refresh
}

output "retry" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.retry
}

output "serial" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.serial
}

output "ttl" {
  description = "returns a string"
  value       = data.dme_custom_soa_record.this.ttl
}

output "this" {
  value = dme_custom_soa_record.this
}
```

[top](#index)