# google_service_account_access_token

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_service_account_access_token" {
  source = "./modules/google-beta/d/google_service_account_access_token"

  # delegates - (optional) is a type of set of string
  delegates = []
  # lifetime - (optional) is a type of string
  lifetime = null
  # scopes - (required) is a type of set of string
  scopes = []
  # target_service_account - (required) is a type of string
  target_service_account = null
}
```

[top](#index)

### Variables

```terraform
variable "delegates" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "lifetime" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scopes" {
  description = "(required)"
  type        = set(string)
}

variable "target_service_account" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_service_account_access_token" "this" {
  # delegates - (optional) is a type of set of string
  delegates = var.delegates
  # lifetime - (optional) is a type of string
  lifetime = var.lifetime
  # scopes - (required) is a type of set of string
  scopes = var.scopes
  # target_service_account - (required) is a type of string
  target_service_account = var.target_service_account
}
```

[top](#index)

### Outputs

```terraform
output "access_token" {
  description = "returns a string"
  value       = data.google_service_account_access_token.this.access_token
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.google_service_account_access_token.this.id
}

output "this" {
  value = google_service_account_access_token.this
}
```

[top](#index)