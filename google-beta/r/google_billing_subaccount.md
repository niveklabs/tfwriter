# google_billing_subaccount

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
module "google_billing_subaccount" {
  source = "./modules/google-beta/r/google_billing_subaccount"

  # deletion_policy - (optional) is a type of string
  deletion_policy = null
  # display_name - (required) is a type of string
  display_name = null
  # master_billing_account - (required) is a type of string
  master_billing_account = null
}
```

[top](#index)

### Variables

```terraform
variable "deletion_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "master_billing_account" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_billing_subaccount" "this" {
  deletion_policy        = var.deletion_policy
  display_name           = var.display_name
  master_billing_account = var.master_billing_account
}
```

[top](#index)

### Outputs

```terraform
output "billing_account_id" {
  description = "returns a string"
  value       = google_billing_subaccount.this.billing_account_id
}

output "id" {
  description = "returns a string"
  value       = google_billing_subaccount.this.id
}

output "name" {
  description = "returns a string"
  value       = google_billing_subaccount.this.name
}

output "open" {
  description = "returns a bool"
  value       = google_billing_subaccount.this.open
}

output "this" {
  value = google_billing_subaccount.this
}
```

[top](#index)