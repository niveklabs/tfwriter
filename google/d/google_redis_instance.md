# google_redis_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_redis_instance" {
  source = "./modules/google/d/google_redis_instance"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The ID of the instance or a fully qualified identifier for the instance."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The name of the Redis region of the instance."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_redis_instance" "this" {
  name    = var.name
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "alternative_location_id" {
  description = "returns a string"
  value       = data.google_redis_instance.this.alternative_location_id
}

output "auth_enabled" {
  description = "returns a bool"
  value       = data.google_redis_instance.this.auth_enabled
}

output "auth_string" {
  description = "returns a string"
  value       = data.google_redis_instance.this.auth_string
}

output "authorized_network" {
  description = "returns a string"
  value       = data.google_redis_instance.this.authorized_network
}

output "connect_mode" {
  description = "returns a string"
  value       = data.google_redis_instance.this.connect_mode
}

output "create_time" {
  description = "returns a string"
  value       = data.google_redis_instance.this.create_time
}

output "current_location_id" {
  description = "returns a string"
  value       = data.google_redis_instance.this.current_location_id
}

output "display_name" {
  description = "returns a string"
  value       = data.google_redis_instance.this.display_name
}

output "host" {
  description = "returns a string"
  value       = data.google_redis_instance.this.host
}

output "id" {
  description = "returns a string"
  value       = data.google_redis_instance.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_redis_instance.this.labels
}

output "location_id" {
  description = "returns a string"
  value       = data.google_redis_instance.this.location_id
}

output "memory_size_gb" {
  description = "returns a number"
  value       = data.google_redis_instance.this.memory_size_gb
}

output "persistence_iam_identity" {
  description = "returns a string"
  value       = data.google_redis_instance.this.persistence_iam_identity
}

output "port" {
  description = "returns a number"
  value       = data.google_redis_instance.this.port
}

output "redis_configs" {
  description = "returns a map of string"
  value       = data.google_redis_instance.this.redis_configs
}

output "redis_version" {
  description = "returns a string"
  value       = data.google_redis_instance.this.redis_version
}

output "reserved_ip_range" {
  description = "returns a string"
  value       = data.google_redis_instance.this.reserved_ip_range
}

output "tier" {
  description = "returns a string"
  value       = data.google_redis_instance.this.tier
}

output "this" {
  value = google_redis_instance.this
}
```

[top](#index)