# avi_backupconfiguration

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_backupconfiguration" {
  source = "./modules/avi/d/avi_backupconfiguration"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_backupconfiguration" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "aws_access_key" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.aws_access_key
}

output "aws_bucket_id" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.aws_bucket_id
}

output "aws_secret_access" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.aws_secret_access
}

output "backup_file_prefix" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.backup_file_prefix
}

output "backup_passphrase" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.backup_passphrase
}

output "id" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.id
}

output "maximum_backups_stored" {
  description = "returns a number"
  value       = data.avi_backupconfiguration.this.maximum_backups_stored
}

output "name" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.name
}

output "remote_directory" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.remote_directory
}

output "remote_hostname" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.remote_hostname
}

output "save_local" {
  description = "returns a bool"
  value       = data.avi_backupconfiguration.this.save_local
}

output "ssh_user_ref" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.ssh_user_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.tenant_ref
}

output "upload_to_remote_host" {
  description = "returns a bool"
  value       = data.avi_backupconfiguration.this.upload_to_remote_host
}

output "upload_to_s3" {
  description = "returns a bool"
  value       = data.avi_backupconfiguration.this.upload_to_s3
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_backupconfiguration.this.uuid
}

output "this" {
  value = avi_backupconfiguration.this
}
```

[top](#index)