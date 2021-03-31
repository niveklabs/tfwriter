# google_service_account_key

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_service_account_key" {
  source = "./modules/google-beta/r/google_service_account_key"

  # keepers - (optional) is a type of map of string
  keepers = {}
  # key_algorithm - (optional) is a type of string
  key_algorithm = null
  # private_key_type - (optional) is a type of string
  private_key_type = null
  # public_key_data - (optional) is a type of string
  public_key_data = null
  # public_key_type - (optional) is a type of string
  public_key_type = null
  # service_account_id - (required) is a type of string
  service_account_id = null
}
```

[top](#index)

### Variables

```terraform
variable "keepers" {
  description = "(optional) - Arbitrary map of values that, when changed, will trigger recreation of resource."
  type        = map(string)
  default     = null
}

variable "key_algorithm" {
  description = "(optional) - The algorithm used to generate the key, used only on create. KEY_ALG_RSA_2048 is the default algorithm. Valid values are: \"KEY_ALG_RSA_1024\", \"KEY_ALG_RSA_2048\"."
  type        = string
  default     = null
}

variable "private_key_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_key_data" {
  description = "(optional) - A field that allows clients to upload their own public key. If set, use this public key data to create a service account key for given service account. Please note, the expected format for this field is a base64 encoded X509_PEM."
  type        = string
  default     = null
}

variable "public_key_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_account_id" {
  description = "(required) - The ID of the parent service account of the key. This can be a string in the format {ACCOUNT} or projects/{PROJECT_ID}/serviceAccounts/{ACCOUNT}, where {ACCOUNT} is the email address or unique id of the service account. If the {ACCOUNT} syntax is used, the project will be inferred from the account."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_service_account_key" "this" {
  keepers            = var.keepers
  key_algorithm      = var.key_algorithm
  private_key_type   = var.private_key_type
  public_key_data    = var.public_key_data
  public_key_type    = var.public_key_type
  service_account_id = var.service_account_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_service_account_key.this.id
}

output "name" {
  description = "returns a string"
  value       = google_service_account_key.this.name
}

output "private_key" {
  description = "returns a string"
  value       = google_service_account_key.this.private_key
  sensitive   = true
}

output "public_key" {
  description = "returns a string"
  value       = google_service_account_key.this.public_key
}

output "valid_after" {
  description = "returns a string"
  value       = google_service_account_key.this.valid_after
}

output "valid_before" {
  description = "returns a string"
  value       = google_service_account_key.this.valid_before
}

output "this" {
  value = google_service_account_key.this
}
```

[top](#index)