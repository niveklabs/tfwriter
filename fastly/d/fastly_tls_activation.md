# fastly_tls_activation

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
module "fastly_tls_activation" {
  source = "./modules/fastly/d/fastly_tls_activation"

  # certificate_id - (optional) is a type of string
  certificate_id = null
  # configuration_id - (optional) is a type of string
  configuration_id = null
  # domain - (optional) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(optional) - ID of the TLS Certificate used."
  type        = string
  default     = null
}

variable "configuration_id" {
  description = "(optional) - ID of the TLS Configuration used."
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional) - Domain that TLS was enabled on."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_activation" "this" {
  # certificate_id - (optional) is a type of string
  certificate_id = var.certificate_id
  # configuration_id - (optional) is a type of string
  configuration_id = var.configuration_id
  # domain - (optional) is a type of string
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "certificate_id" {
  description = "returns a string"
  value       = data.fastly_tls_activation.this.certificate_id
}

output "configuration_id" {
  description = "returns a string"
  value       = data.fastly_tls_activation.this.configuration_id
}

output "created_at" {
  description = "returns a string"
  value       = data.fastly_tls_activation.this.created_at
}

output "domain" {
  description = "returns a string"
  value       = data.fastly_tls_activation.this.domain
}

output "id" {
  description = "returns a string"
  value       = data.fastly_tls_activation.this.id
}

output "this" {
  value = fastly_tls_activation.this
}
```

[top](#index)