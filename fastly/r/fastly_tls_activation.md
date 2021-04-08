# fastly_tls_activation

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_activation" {
  source = "./modules/fastly/r/fastly_tls_activation"

  # certificate_id - (required) is a type of string
  certificate_id = null
  # configuration_id - (optional) is a type of string
  configuration_id = null
  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(required) - ID of certificate to use. Must have the `domain` specified in the certificate's Subject Alternative Names."
  type        = string
}

variable "configuration_id" {
  description = "(optional) - ID of TLS configuration to be used to terminate TLS traffic, or use the default one if missing."
  type        = string
  default     = null
}

variable "domain" {
  description = "(required) - Domain to enable TLS on. Must be assigned to an existing Fastly Service."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fastly_tls_activation" "this" {
  # certificate_id - (required) is a type of string
  certificate_id = var.certificate_id
  # configuration_id - (optional) is a type of string
  configuration_id = var.configuration_id
  # domain - (required) is a type of string
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "configuration_id" {
  description = "returns a string"
  value       = fastly_tls_activation.this.configuration_id
}

output "created_at" {
  description = "returns a string"
  value       = fastly_tls_activation.this.created_at
}

output "id" {
  description = "returns a string"
  value       = fastly_tls_activation.this.id
}

output "this" {
  value = fastly_tls_activation.this
}
```

[top](#index)