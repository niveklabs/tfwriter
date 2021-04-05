# google_organization

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
module "google_organization" {
  source = "./modules/google-beta/d/google_organization"

  # domain - (optional) is a type of string
  domain = null
  # organization - (optional) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "organization" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_organization" "this" {
  domain       = var.domain
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = data.google_organization.this.create_time
}

output "directory_customer_id" {
  description = "returns a string"
  value       = data.google_organization.this.directory_customer_id
}

output "domain" {
  description = "returns a string"
  value       = data.google_organization.this.domain
}

output "id" {
  description = "returns a string"
  value       = data.google_organization.this.id
}

output "lifecycle_state" {
  description = "returns a string"
  value       = data.google_organization.this.lifecycle_state
}

output "name" {
  description = "returns a string"
  value       = data.google_organization.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.google_organization.this.org_id
}

output "this" {
  value = google_organization.this
}
```

[top](#index)