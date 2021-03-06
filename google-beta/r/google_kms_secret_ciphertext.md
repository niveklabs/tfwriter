# google_kms_secret_ciphertext

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_secret_ciphertext" {
  source = "./modules/google-beta/r/google_kms_secret_ciphertext"

  # additional_authenticated_data - (optional) is a type of string
  additional_authenticated_data = null
  # crypto_key - (required) is a type of string
  crypto_key = null
  # plaintext - (required) is a type of string
  plaintext = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "additional_authenticated_data" {
  description = "(optional) - The additional authenticated data used for integrity checks during encryption and decryption."
  type        = string
  default     = null
}

variable "crypto_key" {
  description = "(required) - The full name of the CryptoKey that will be used to encrypt the provided plaintext.\nFormat: ''projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}/cryptoKeys/{{cryptoKey}}''"
  type        = string
}

variable "plaintext" {
  description = "(required) - The plaintext to be encrypted."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_kms_secret_ciphertext" "this" {
  # additional_authenticated_data - (optional) is a type of string
  additional_authenticated_data = var.additional_authenticated_data
  # crypto_key - (required) is a type of string
  crypto_key = var.crypto_key
  # plaintext - (required) is a type of string
  plaintext = var.plaintext

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ciphertext" {
  description = "returns a string"
  value       = google_kms_secret_ciphertext.this.ciphertext
}

output "id" {
  description = "returns a string"
  value       = google_kms_secret_ciphertext.this.id
}

output "this" {
  value = google_kms_secret_ciphertext.this
}
```

[top](#index)