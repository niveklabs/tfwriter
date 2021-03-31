# google_billing_account

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_billing_account" {
  source = "./modules/google-beta/d/google_billing_account"

  # billing_account - (optional) is a type of string
  billing_account = null
  # display_name - (optional) is a type of string
  display_name = null
  # open - (optional) is a type of bool
  open = null
}
```

[top](#index)

### Variables

```terraform
variable "billing_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "open" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_billing_account" "this" {
  billing_account = var.billing_account
  display_name    = var.display_name
  open            = var.open
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_billing_account.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_billing_account.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_billing_account.this.name
}

output "open" {
  description = "returns a bool"
  value       = data.google_billing_account.this.open
}

output "project_ids" {
  description = "returns a set of string"
  value       = data.google_billing_account.this.project_ids
}

output "this" {
  value = google_billing_account.this
}
```

[top](#index)