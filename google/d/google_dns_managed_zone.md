# google_dns_managed_zone

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
module "google_dns_managed_zone" {
  source = "./modules/google/d/google_dns_managed_zone"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "google_dns_managed_zone" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = data.google_dns_managed_zone.this.description
}

output "dns_name" {
  description = "returns a string"
  value       = data.google_dns_managed_zone.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = data.google_dns_managed_zone.this.id
}

output "name_servers" {
  description = "returns a list of string"
  value       = data.google_dns_managed_zone.this.name_servers
}

output "visibility" {
  description = "returns a string"
  value       = data.google_dns_managed_zone.this.visibility
}

output "this" {
  value = google_dns_managed_zone.this
}
```

[top](#index)