# fastly_tls_configuration

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_configuration" {
  source = "./modules/fastly/d/fastly_tls_configuration"

  # default - (optional) is a type of bool
  default = null
  # http_protocols - (optional) is a type of set of string
  http_protocols = []
  # name - (optional) is a type of string
  name = null
  # tls_protocols - (optional) is a type of set of string
  tls_protocols = []
  # tls_service - (optional) is a type of string
  tls_service = null
}
```

[top](#index)

### Variables

```terraform
variable "default" {
  description = "(optional) - Signifies whether Fastly will use this configuration as a default when creating a new TLS activation."
  type        = bool
  default     = null
}

variable "http_protocols" {
  description = "(optional) - HTTP protocols available on the TLS configuration."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - Custom name of the TLS configuration."
  type        = string
  default     = null
}

variable "tls_protocols" {
  description = "(optional) - TLS protocols available on the TLS configuration."
  type        = set(string)
  default     = null
}

variable "tls_service" {
  description = "(optional) - Whether the configuration should support the `PLATFORM` or `CUSTOM` TLS service."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_configuration" "this" {
  # default - (optional) is a type of bool
  default = var.default
  # http_protocols - (optional) is a type of set of string
  http_protocols = var.http_protocols
  # name - (optional) is a type of string
  name = var.name
  # tls_protocols - (optional) is a type of set of string
  tls_protocols = var.tls_protocols
  # tls_service - (optional) is a type of string
  tls_service = var.tls_service
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.fastly_tls_configuration.this.created_at
}

output "default" {
  description = "returns a bool"
  value       = data.fastly_tls_configuration.this.default
}

output "dns_records" {
  description = "returns a set of object"
  value       = data.fastly_tls_configuration.this.dns_records
}

output "http_protocols" {
  description = "returns a set of string"
  value       = data.fastly_tls_configuration.this.http_protocols
}

output "id" {
  description = "returns a string"
  value       = data.fastly_tls_configuration.this.id
}

output "name" {
  description = "returns a string"
  value       = data.fastly_tls_configuration.this.name
}

output "tls_protocols" {
  description = "returns a set of string"
  value       = data.fastly_tls_configuration.this.tls_protocols
}

output "tls_service" {
  description = "returns a string"
  value       = data.fastly_tls_configuration.this.tls_service
}

output "updated_at" {
  description = "returns a string"
  value       = data.fastly_tls_configuration.this.updated_at
}

output "this" {
  value = fastly_tls_configuration.this
}
```

[top](#index)