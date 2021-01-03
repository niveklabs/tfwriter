# google_container_engine_versions

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_container_engine_versions" {
  source = "./modules/google-beta/d/google_container_engine_versions"

  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
  # version_prefix - (optional) is a type of string
  version_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_container_engine_versions" "this" {
  location       = var.location
  project        = var.project
  version_prefix = var.version_prefix
}
```

[top](#index)

### Outputs

```terraform
output "default_cluster_version" {
  description = "returns a string"
  value       = data.google_container_engine_versions.this.default_cluster_version
}

output "id" {
  description = "returns a string"
  value       = data.google_container_engine_versions.this.id
}

output "latest_master_version" {
  description = "returns a string"
  value       = data.google_container_engine_versions.this.latest_master_version
}

output "latest_node_version" {
  description = "returns a string"
  value       = data.google_container_engine_versions.this.latest_node_version
}

output "release_channel_default_version" {
  description = "returns a map of string"
  value       = data.google_container_engine_versions.this.release_channel_default_version
}

output "valid_master_versions" {
  description = "returns a list of string"
  value       = data.google_container_engine_versions.this.valid_master_versions
}

output "valid_node_versions" {
  description = "returns a list of string"
  value       = data.google_container_engine_versions.this.valid_node_versions
}

output "this" {
  value = google_container_engine_versions.this
}
```

[top](#index)