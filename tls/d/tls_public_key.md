# tls_public_key

[back](../tls.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tls = ">= 3.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tls_public_key" {
  source = "./modules/tls/d/tls_public_key"

  # private_key_pem - (required) is a type of string
  private_key_pem = null
}
```

[top](#index)

### Variables

```terraform
variable "private_key_pem" {
  description = "(required) - PEM formatted string to use as the private key"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tls_public_key" "this" {
  private_key_pem = var.private_key_pem
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.tls_public_key.this.algorithm
}

output "id" {
  description = "returns a string"
  value       = data.tls_public_key.this.id
}

output "public_key_fingerprint_md5" {
  description = "returns a string"
  value       = data.tls_public_key.this.public_key_fingerprint_md5
}

output "public_key_openssh" {
  description = "returns a string"
  value       = data.tls_public_key.this.public_key_openssh
}

output "public_key_pem" {
  description = "returns a string"
  value       = data.tls_public_key.this.public_key_pem
}

output "this" {
  value = tls_public_key.this
}
```

[top](#index)