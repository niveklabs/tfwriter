# google_client_config

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
module "google_client_config" {
  source = "./modules/google-beta/d/google_client_config"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "google_client_config" "this" {
}
```

[top](#index)

### Outputs

```terraform
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