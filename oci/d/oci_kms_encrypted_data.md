# oci_kms_encrypted_data

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_kms_encrypted_data" {
  source = "./modules/oci/d/oci_kms_encrypted_data"

  # associated_data - (optional) is a type of map of string
  associated_data = {}
  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = null
  # key_id - (required) is a type of string
  key_id = null
  # plaintext - (required) is a type of string
  plaintext = null
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

variable "crypto_endpoint" {
  description = "(required)"
  type        = string
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "plaintext" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_kms_encrypted_data" "this" {
  associated_data = var.associated_data
  crypto_endpoint = var.crypto_endpoint
  key_id          = var.key_id
  plaintext       = var.plaintext
}
```

[top](#index)

### Outputs

```terraform
output "ciphertext" {
  description = "returns a string"
  value       = data.oci_kms_encrypted_data.this.ciphertext
}

output "id" {
  description = "returns a string"
  value       = data.oci_kms_encrypted_data.this.id
}

output "this" {
  value = oci_kms_encrypted_data.this
}
```

[top](#index)