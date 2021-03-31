# oci_kms_generated_key

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
module "oci_kms_generated_key" {
  source = "./modules/oci/r/oci_kms_generated_key"

  # associated_data - (optional) is a type of map of string
  associated_data = {}
  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = null
  # include_plaintext_key - (required) is a type of bool
  include_plaintext_key = null
  # key_id - (required) is a type of string
  key_id = null
  # logging_context - (optional) is a type of map of string
  logging_context = {}

  key_shape = [{
    algorithm = null
    curve_id  = null
    length    = null
  }]

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

variable "include_plaintext_key" {
  description = "(required)"
  type        = bool
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "logging_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "key_shape" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      algorithm = string
      curve_id  = string
      length    = number
    }
  ))
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
resource "oci_kms_generated_key" "this" {
  associated_data       = var.associated_data
  crypto_endpoint       = var.crypto_endpoint
  include_plaintext_key = var.include_plaintext_key
  key_id                = var.key_id
  logging_context       = var.logging_context

  dynamic "key_shape" {
    for_each = var.key_shape
    content {
      algorithm = key_shape.value["algorithm"]
      curve_id  = key_shape.value["curve_id"]
      length    = key_shape.value["length"]
    }
  }

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
  value       = oci_kms_generated_key.this.ciphertext
}

output "id" {
  description = "returns a string"
  value       = oci_kms_generated_key.this.id
}

output "plaintext" {
  description = "returns a string"
  value       = oci_kms_generated_key.this.plaintext
}

output "plaintext_checksum" {
  description = "returns a string"
  value       = oci_kms_generated_key.this.plaintext_checksum
}

output "this" {
  value = oci_kms_generated_key.this
}
```

[top](#index)