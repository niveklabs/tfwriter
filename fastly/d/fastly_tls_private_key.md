# fastly_tls_private_key

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
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_private_key" {
  source = "./modules/fastly/d/fastly_tls_private_key"

  # created_at - (optional) is a type of string
  created_at = null
  # key_length - (optional) is a type of number
  key_length = null
  # key_type - (optional) is a type of string
  key_type = null
  # name - (optional) is a type of string
  name = null
  # public_key_sha1 - (optional) is a type of string
  public_key_sha1 = null
}
```

[top](#index)

### Variables

```terraform
variable "created_at" {
  description = "(optional) - Timestamp (GMT) when the private key was created."
  type        = string
  default     = null
}

variable "key_length" {
  description = "(optional) - The key length used to generate the private key."
  type        = number
  default     = null
}

variable "key_type" {
  description = "(optional) - The algorithm used to generate the private key. Must be RSA."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The human-readable name assigned to the private key when uploaded."
  type        = string
  default     = null
}

variable "public_key_sha1" {
  description = "(optional) - A hash of the associated public key, useful for safely identifying it."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_private_key" "this" {
  # created_at - (optional) is a type of string
  created_at = var.created_at
  # key_length - (optional) is a type of number
  key_length = var.key_length
  # key_type - (optional) is a type of string
  key_type = var.key_type
  # name - (optional) is a type of string
  name = var.name
  # public_key_sha1 - (optional) is a type of string
  public_key_sha1 = var.public_key_sha1
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.fastly_tls_private_key.this.created_at
}

output "id" {
  description = "returns a string"
  value       = data.fastly_tls_private_key.this.id
}

output "key_length" {
  description = "returns a number"
  value       = data.fastly_tls_private_key.this.key_length
}

output "key_type" {
  description = "returns a string"
  value       = data.fastly_tls_private_key.this.key_type
}

output "name" {
  description = "returns a string"
  value       = data.fastly_tls_private_key.this.name
}

output "public_key_sha1" {
  description = "returns a string"
  value       = data.fastly_tls_private_key.this.public_key_sha1
}

output "replace" {
  description = "returns a bool"
  value       = data.fastly_tls_private_key.this.replace
}

output "this" {
  value = fastly_tls_private_key.this
}
```

[top](#index)