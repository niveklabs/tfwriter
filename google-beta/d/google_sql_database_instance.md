# google_sql_database_instance

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
module "google_sql_database_instance" {
  source = "./modules/google-beta/d/google_sql_database_instance"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the instance. If the name is left blank, Terraform will randomly generate one when the instance is first created. This is done because after a name is used, it cannot be reused for up to one week."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_sql_database_instance" "this" {
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "clone" {
  description = "returns a list of object"
  value       = data.google_sql_database_instance.this.clone
}

output "connection_name" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.connection_name
}

output "database_version" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.database_version
}

output "deletion_protection" {
  description = "returns a bool"
  value       = data.google_sql_database_instance.this.deletion_protection
}

output "encryption_key_name" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.encryption_key_name
}

output "first_ip_address" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.first_ip_address
}

output "id" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.id
}

output "ip_address" {
  description = "returns a list of object"
  value       = data.google_sql_database_instance.this.ip_address
}

output "master_instance_name" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.master_instance_name
}

output "private_ip_address" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.private_ip_address
}

output "public_ip_address" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.public_ip_address
}

output "region" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.region
}

output "replica_configuration" {
  description = "returns a list of object"
  value       = data.google_sql_database_instance.this.replica_configuration
}

output "restore_backup_context" {
  description = "returns a list of object"
  value       = data.google_sql_database_instance.this.restore_backup_context
}

output "root_password" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.root_password
}

output "self_link" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.self_link
}

output "server_ca_cert" {
  description = "returns a list of object"
  value       = data.google_sql_database_instance.this.server_ca_cert
}

output "service_account_email_address" {
  description = "returns a string"
  value       = data.google_sql_database_instance.this.service_account_email_address
}

output "settings" {
  description = "returns a list of object"
  value       = data.google_sql_database_instance.this.settings
}

output "this" {
  value = google_sql_database_instance.this
}
```

[top](#index)