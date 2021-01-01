# google_service_account_id_token

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_service_account_id_token" {
  source = "./modules/google/d/google_service_account_id_token"

  # delegates - (optional) is a type of set of string
  delegates = []
  # include_email - (optional) is a type of bool
  include_email = null
  # target_audience - (required) is a type of string
  target_audience = null
  # target_service_account - (optional) is a type of string
  target_service_account = null
}
```

[top](#index)

### Variables

```hcl
variable "delegates" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "include_email" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "target_audience" {
  description = "(required)"
  type        = string
}

variable "target_service_account" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "google_service_account_id_token" "this" {
  delegates              = var.delegates
  include_email          = var.include_email
  target_audience        = var.target_audience
  target_service_account = var.target_service_account
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_service_account_id_token.this.id
}

output "id_token" {
  description = "returns a string"
  value       = data.google_service_account_id_token.this.id_token
  sensitive   = true
}

output "this" {
  value = google_service_account_id_token.this
}
```

[top](#index)