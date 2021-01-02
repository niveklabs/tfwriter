# google_kms_crypto_key_iam_binding

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_crypto_key_iam_binding" {
  source = "./modules/google/r/google_kms_crypto_key_iam_binding"

  # crypto_key_id - (required) is a type of string
  crypto_key_id = null
  # members - (required) is a type of set of string
  members = []
  # role - (required) is a type of string
  role = null

  condition = [{
    description = null
    expression  = null
    title       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "crypto_key_id" {
  description = "(required)"
  type        = string
}

variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      expression  = string
      title       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_kms_crypto_key_iam_binding" "this" {
  crypto_key_id = var.crypto_key_id
  members       = var.members
  role          = var.role

  dynamic "condition" {
    for_each = var.condition
    content {
      description = condition.value["description"]
      expression  = condition.value["expression"]
      title       = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_kms_crypto_key_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_kms_crypto_key_iam_binding.this.id
}

output "this" {
  value = google_kms_crypto_key_iam_binding.this
}
```

[top](#index)