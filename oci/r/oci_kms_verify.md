# oci_kms_verify

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_kms_verify" {
  source = "./modules/oci/r/oci_kms_verify"

  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = null
  # key_id - (required) is a type of string
  key_id = null
  # key_version_id - (required) is a type of string
  key_version_id = null
  # message - (required) is a type of string
  message = null
  # message_type - (optional) is a type of string
  message_type = null
  # signature - (required) is a type of string
  signature = null
  # signing_algorithm - (required) is a type of string
  signing_algorithm = null

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
variable "crypto_endpoint" {
  description = "(required)"
  type        = string
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "key_version_id" {
  description = "(required)"
  type        = string
}

variable "message" {
  description = "(required)"
  type        = string
}

variable "message_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature" {
  description = "(required)"
  type        = string
}

variable "signing_algorithm" {
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
resource "oci_kms_verify" "this" {
  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = var.crypto_endpoint
  # key_id - (required) is a type of string
  key_id = var.key_id
  # key_version_id - (required) is a type of string
  key_version_id = var.key_version_id
  # message - (required) is a type of string
  message = var.message
  # message_type - (optional) is a type of string
  message_type = var.message_type
  # signature - (required) is a type of string
  signature = var.signature
  # signing_algorithm - (required) is a type of string
  signing_algorithm = var.signing_algorithm

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_kms_verify.this.id
}

output "is_signature_valid" {
  description = "returns a bool"
  value       = oci_kms_verify.this.is_signature_valid
}

output "message_type" {
  description = "returns a string"
  value       = oci_kms_verify.this.message_type
}

output "this" {
  value = oci_kms_verify.this
}
```

[top](#index)