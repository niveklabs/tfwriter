# fastly_tls_private_key

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
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_private_key" {
  source = "./modules/fastly/r/fastly_tls_private_key"

  # key_pem - (required) is a type of string
  key_pem = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "key_pem" {
  description = "(required) - Private key in PEM format."
  type        = string
}

variable "name" {
  description = "(required) - Customisable name of the private key."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fastly_tls_private_key" "this" {
  key_pem = var.key_pem
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = fastly_tls_private_key.this.created_at
}

output "id" {
  description = "returns a string"
  value       = fastly_tls_private_key.this.id
}

output "key_length" {
  description = "returns a number"
  value       = fastly_tls_private_key.this.key_length
}

output "key_type" {
  description = "returns a string"
  value       = fastly_tls_private_key.this.key_type
}

output "public_key_sha1" {
  description = "returns a string"
  value       = fastly_tls_private_key.this.public_key_sha1
}

output "replace" {
  description = "returns a bool"
  value       = fastly_tls_private_key.this.replace
}

output "this" {
  value = fastly_tls_private_key.this
}
```

[top](#index)