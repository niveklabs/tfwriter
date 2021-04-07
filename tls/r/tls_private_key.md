# tls_private_key

[back](../tls.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tls = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tls_private_key" {
  source = "./modules/tls/r/tls_private_key"

  # algorithm - (required) is a type of string
  algorithm = null
  # ecdsa_curve - (optional) is a type of string
  ecdsa_curve = null
  # rsa_bits - (optional) is a type of number
  rsa_bits = null
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(required) - Name of the algorithm to use to generate the private key"
  type        = string
}

variable "ecdsa_curve" {
  description = "(optional) - ECDSA curve to use when generating a key"
  type        = string
  default     = null
}

variable "rsa_bits" {
  description = "(optional) - Number of bits to use when generating an RSA key"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tls_private_key" "this" {
  # algorithm - (required) is a type of string
  algorithm = var.algorithm
  # ecdsa_curve - (optional) is a type of string
  ecdsa_curve = var.ecdsa_curve
  # rsa_bits - (optional) is a type of number
  rsa_bits = var.rsa_bits
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tls_private_key.this.id
}

output "private_key_pem" {
  description = "returns a string"
  value       = tls_private_key.this.private_key_pem
  sensitive   = true
}

output "public_key_fingerprint_md5" {
  description = "returns a string"
  value       = tls_private_key.this.public_key_fingerprint_md5
}

output "public_key_openssh" {
  description = "returns a string"
  value       = tls_private_key.this.public_key_openssh
}

output "public_key_pem" {
  description = "returns a string"
  value       = tls_private_key.this.public_key_pem
}

output "this" {
  value = tls_private_key.this
}
```

[top](#index)