# fastly_tls_subscription

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
module "fastly_tls_subscription" {
  source = "./modules/fastly/d/fastly_tls_subscription"

  # certificate_authority - (optional) is a type of string
  certificate_authority = null
  # configuration_id - (optional) is a type of string
  configuration_id = null
  # domains - (optional) is a type of set of string
  domains = []
}
```

[top](#index)

### Variables

```terraform
variable "certificate_authority" {
  description = "(optional) - The entity that issues and certifies the TLS certificates for the subscription."
  type        = string
  default     = null
}

variable "configuration_id" {
  description = "(optional) - ID of TLS configuration used to terminate TLS traffic."
  type        = string
  default     = null
}

variable "domains" {
  description = "(optional) - List of domains on which to enable TLS."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_subscription" "this" {
  certificate_authority = var.certificate_authority
  configuration_id      = var.configuration_id
  domains               = var.domains
}
```

[top](#index)

### Outputs

```terraform
output "certificate_authority" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.certificate_authority
}

output "common_name" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.common_name
}

output "configuration_id" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.configuration_id
}

output "created_at" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.created_at
}

output "domains" {
  description = "returns a set of string"
  value       = data.fastly_tls_subscription.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.id
}

output "state" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.state
}

output "updated_at" {
  description = "returns a string"
  value       = data.fastly_tls_subscription.this.updated_at
}

output "this" {
  value = fastly_tls_subscription.this
}
```

[top](#index)