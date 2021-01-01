# google_logging_organization_bucket_config

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
module "google_logging_organization_bucket_config" {
  source = "./modules/google/r/google_logging_organization_bucket_config"

  # bucket_id - (required) is a type of string
  bucket_id = null
  # description - (optional) is a type of string
  description = null
  # location - (required) is a type of string
  location = null
  # organization - (required) is a type of string
  organization = null
  # retention_days - (optional) is a type of number
  retention_days = null
}
```

[top](#index)

### Variables

```hcl
variable "bucket_id" {
  description = "(required) - The name of the logging bucket. Logging automatically creates two log buckets: _Required and _Default."
  type        = string
}

variable "description" {
  description = "(optional) - An optional description for this bucket."
  type        = string
  default     = null
}

variable "location" {
  description = "(required) - The location of the bucket."
  type        = string
}

variable "organization" {
  description = "(required) - The parent resource that contains the logging bucket."
  type        = string
}

variable "retention_days" {
  description = "(optional) - Logs will be retained by default for this amount of time, after which they will automatically be deleted. The minimum retention period is 1 day. If this value is set to zero at bucket creation time, the default time of 30 days will be used."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "google_logging_organization_bucket_config" "this" {
  bucket_id      = var.bucket_id
  description    = var.description
  location       = var.location
  organization   = var.organization
  retention_days = var.retention_days
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = google_logging_organization_bucket_config.this.description
}

output "id" {
  description = "returns a string"
  value       = google_logging_organization_bucket_config.this.id
}

output "lifecycle_state" {
  description = "returns a string"
  value       = google_logging_organization_bucket_config.this.lifecycle_state
}

output "name" {
  description = "returns a string"
  value       = google_logging_organization_bucket_config.this.name
}

output "this" {
  value = google_logging_organization_bucket_config.this
}
```

[top](#index)