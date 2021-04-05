# google_dns_keys

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
module "google_dns_keys" {
  source = "./modules/google-beta/d/google_dns_keys"

  # managed_zone - (required) is a type of string
  managed_zone = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_zone" {
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

```terraform
data "google_dns_keys" "this" {
  managed_zone = var.managed_zone
  project      = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_dns_keys.this.id
}

output "key_signing_keys" {
  description = "returns a list of object"
  value       = data.google_dns_keys.this.key_signing_keys
}

output "project" {
  description = "returns a string"
  value       = data.google_dns_keys.this.project
}

output "zone_signing_keys" {
  description = "returns a list of object"
  value       = data.google_dns_keys.this.zone_signing_keys
}

output "this" {
  value = google_dns_keys.this
}
```

[top](#index)