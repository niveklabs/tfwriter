# fastly_tls_domain

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
module "fastly_tls_domain" {
  source = "./modules/fastly/d/fastly_tls_domain"

  # domain - (required) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - Domain name to look up activations, certificates and subscriptions for."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_domain" "this" {
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fastly_tls_domain.this.id
}

output "tls_activation_ids" {
  description = "returns a set of string"
  value       = data.fastly_tls_domain.this.tls_activation_ids
}

output "tls_certificate_ids" {
  description = "returns a set of string"
  value       = data.fastly_tls_domain.this.tls_certificate_ids
}

output "tls_subscription_ids" {
  description = "returns a set of string"
  value       = data.fastly_tls_domain.this.tls_subscription_ids
}

output "this" {
  value = fastly_tls_domain.this
}
```

[top](#index)