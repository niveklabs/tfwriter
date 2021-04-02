# oci_kms_decrypted_data

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_kms_decrypted_data" {
  source = "./modules/oci/d/oci_kms_decrypted_data"

  # associated_data - (optional) is a type of map of string
  associated_data = {}
  # ciphertext - (required) is a type of string
  ciphertext = null
  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = null
  # key_id - (required) is a type of string
  key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "associated_data" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ciphertext" {
  description = "(required)"
  type        = string
}

variable "crypto_endpoint" {
  description = "(required)"
  type        = string
}

variable "key_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_kms_decrypted_data" "this" {
  associated_data = var.associated_data
  ciphertext      = var.ciphertext
  crypto_endpoint = var.crypto_endpoint
  key_id          = var.key_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_kms_decrypted_data.this.id
}

output "plaintext" {
  description = "returns a string"
  value       = data.oci_kms_decrypted_data.this.plaintext
}

output "plaintext_checksum" {
  description = "returns a string"
  value       = data.oci_kms_decrypted_data.this.plaintext_checksum
}

output "this" {
  value = oci_kms_decrypted_data.this
}
```

[top](#index)