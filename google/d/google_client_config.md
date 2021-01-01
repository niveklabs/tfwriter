# google_client_config

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
module "google_client_config" {
  source = "./modules/google/d/google_client_config"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "google_client_config" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "access_token" {
  description = "returns a string"
  value       = data.google_client_config.this.access_token
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.google_client_config.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_client_config.this.project
}

output "region" {
  description = "returns a string"
  value       = data.google_client_config.this.region
}

output "zone" {
  description = "returns a string"
  value       = data.google_client_config.this.zone
}

output "this" {
  value = google_client_config.this
}
```

[top](#index)