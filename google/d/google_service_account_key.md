# google_service_account_key

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_service_account_key" {
  source = "./modules/google/d/google_service_account_key"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # public_key_type - (optional) is a type of string
  public_key_type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_key_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_service_account_key" "this" {
  name            = var.name
  project         = var.project
  public_key_type = var.public_key_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_service_account_key.this.id
}

output "key_algorithm" {
  description = "returns a string"
  value       = data.google_service_account_key.this.key_algorithm
}

output "public_key" {
  description = "returns a string"
  value       = data.google_service_account_key.this.public_key
}

output "this" {
  value = google_service_account_key.this
}
```

[top](#index)