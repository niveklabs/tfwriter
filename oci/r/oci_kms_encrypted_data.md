# oci_kms_encrypted_data

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_kms_encrypted_data" {
  source = "./modules/oci/r/oci_kms_encrypted_data"

  # associated_data - (optional) is a type of map of string
  associated_data = {}
  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = null
  # encryption_algorithm - (optional) is a type of string
  encryption_algorithm = null
  # key_id - (required) is a type of string
  key_id = null
  # key_version_id - (optional) is a type of string
  key_version_id = null
  # logging_context - (optional) is a type of map of string
  logging_context = {}
  # plaintext - (required) is a type of string
  plaintext = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
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

variable "encryption_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "key_version_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logging_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "plaintext" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_kms_encrypted_data" "this" {
  associated_data      = var.associated_data
  crypto_endpoint      = var.crypto_endpoint
  encryption_algorithm = var.encryption_algorithm
  key_id               = var.key_id
  key_version_id       = var.key_version_id
  logging_context      = var.logging_context
  plaintext            = var.plaintext

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ciphertext" {
  description = "returns a string"
  value       = oci_kms_encrypted_data.this.ciphertext
}

output "encryption_algorithm" {
  description = "returns a string"
  value       = oci_kms_encrypted_data.this.encryption_algorithm
}

output "id" {
  description = "returns a string"
  value       = oci_kms_encrypted_data.this.id
}

output "key_version_id" {
  description = "returns a string"
  value       = oci_kms_encrypted_data.this.key_version_id
}

output "this" {
  value = oci_kms_encrypted_data.this
}
```

[top](#index)