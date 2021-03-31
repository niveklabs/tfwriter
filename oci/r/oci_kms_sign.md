# oci_kms_sign

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
module "oci_kms_sign" {
  source = "./modules/oci/r/oci_kms_sign"

  # crypto_endpoint - (required) is a type of string
  crypto_endpoint = null
  # key_id - (required) is a type of string
  key_id = null
  # key_version_id - (optional) is a type of string
  key_version_id = null
  # message - (required) is a type of string
  message = null
  # message_type - (optional) is a type of string
  message_type = null
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
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_kms_sign" "this" {
  crypto_endpoint   = var.crypto_endpoint
  key_id            = var.key_id
  key_version_id    = var.key_version_id
  message           = var.message
  message_type      = var.message_type
  signing_algorithm = var.signing_algorithm

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
output "id" {
  description = "returns a string"
  value       = oci_kms_sign.this.id
}

output "key_version_id" {
  description = "returns a string"
  value       = oci_kms_sign.this.key_version_id
}

output "message_type" {
  description = "returns a string"
  value       = oci_kms_sign.this.message_type
}

output "signature" {
  description = "returns a string"
  value       = oci_kms_sign.this.signature
}

output "this" {
  value = oci_kms_sign.this
}
```

[top](#index)