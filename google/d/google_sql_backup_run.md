# google_sql_backup_run

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
module "google_sql_backup_run" {
  source = "./modules/google/d/google_sql_backup_run"

  # backup_id - (optional) is a type of number
  backup_id = null
  # instance - (required) is a type of string
  instance = null
  # most_recent - (optional) is a type of bool
  most_recent = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_id" {
  description = "(optional) - The identifier for this backup run. Unique only for a specific Cloud SQL instance. If left empty and multiple backups exist for the instance, most_recent must be set to true."
  type        = number
  default     = null
}

variable "instance" {
  description = "(required) - Name of the database instance."
  type        = string
}

variable "most_recent" {
  description = "(optional) - Toggles use of the most recent backup run if multiple backups exist for a Cloud SQL instance."
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_sql_backup_run" "this" {
  # backup_id - (optional) is a type of number
  backup_id = var.backup_id
  # instance - (required) is a type of string
  instance = var.instance
  # most_recent - (optional) is a type of bool
  most_recent = var.most_recent
}
```

[top](#index)

### Outputs

```terraform
output "backup_id" {
  description = "returns a number"
  value       = data.google_sql_backup_run.this.backup_id
}

output "id" {
  description = "returns a string"
  value       = data.google_sql_backup_run.this.id
}

output "location" {
  description = "returns a string"
  value       = data.google_sql_backup_run.this.location
}

output "start_time" {
  description = "returns a string"
  value       = data.google_sql_backup_run.this.start_time
}

output "status" {
  description = "returns a string"
  value       = data.google_sql_backup_run.this.status
}

output "this" {
  value = google_sql_backup_run.this
}
```

[top](#index)