# cloudflare_origin_ca_certificate

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_origin_ca_certificate" {
  source = "./modules/cloudflare/r/cloudflare_origin_ca_certificate"

  # csr - (required) is a type of string
  csr = null
  # hostnames - (required) is a type of set of string
  hostnames = []
  # request_type - (required) is a type of string
  request_type = null
  # requested_validity - (optional) is a type of number
  requested_validity = null
}
```

[top](#index)

### Variables

```terraform
variable "csr" {
  description = "(required)"
  type        = string
}

variable "hostnames" {
  description = "(required)"
  type        = set(string)
}

variable "request_type" {
  description = "(required)"
  type        = string
}

variable "requested_validity" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_origin_ca_certificate" "this" {
  csr                = var.csr
  hostnames          = var.hostnames
  request_type       = var.request_type
  requested_validity = var.requested_validity
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = cloudflare_origin_ca_certificate.this.certificate
}

output "expires_on" {
  description = "returns a string"
  value       = cloudflare_origin_ca_certificate.this.expires_on
}

output "id" {
  description = "returns a string"
  value       = cloudflare_origin_ca_certificate.this.id
}

output "this" {
  value = cloudflare_origin_ca_certificate.this
}
```

[top](#index)