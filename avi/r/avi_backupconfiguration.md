# avi_backupconfiguration

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/avi/r/avi_backupconfiguration"

  # aws_access_key - (optional) is a type of string
  aws_access_key = null
  # aws_bucket_id - (optional) is a type of string
  aws_bucket_id = null
  # aws_secret_access - (optional) is a type of string
  aws_secret_access = null
  # backup_file_prefix - (optional) is a type of string
  backup_file_prefix = null
  # backup_passphrase - (optional) is a type of string
  backup_passphrase = null
  # maximum_backups_stored - (optional) is a type of number
  maximum_backups_stored = null
  # name - (required) is a type of string
  name = null
  # remote_directory - (optional) is a type of string
  remote_directory = null
  # remote_hostname - (optional) is a type of string
  remote_hostname = null
  # save_local - (optional) is a type of bool
  save_local = null
  # ssh_user_ref - (optional) is a type of string
  ssh_user_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # upload_to_remote_host - (optional) is a type of bool
  upload_to_remote_host = null
  # upload_to_s3 - (optional) is a type of bool
  upload_to_s3 = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_access_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_bucket_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_secret_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_file_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maximum_backups_stored" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "remote_directory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "save_local" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssh_user_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_to_remote_host" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "upload_to_s3" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_backupconfiguration" "this" {
  # aws_access_key - (optional) is a type of string
  aws_access_key = var.aws_access_key
  # aws_bucket_id - (optional) is a type of string
  aws_bucket_id = var.aws_bucket_id
  # aws_secret_access - (optional) is a type of string
  aws_secret_access = var.aws_secret_access
  # backup_file_prefix - (optional) is a type of string
  backup_file_prefix = var.backup_file_prefix
  # backup_passphrase - (optional) is a type of string
  backup_passphrase = var.backup_passphrase
  # maximum_backups_stored - (optional) is a type of number
  maximum_backups_stored = var.maximum_backups_stored
  # name - (required) is a type of string
  name = var.name
  # remote_directory - (optional) is a type of string
  remote_directory = var.remote_directory
  # remote_hostname - (optional) is a type of string
  remote_hostname = var.remote_hostname
  # save_local - (optional) is a type of bool
  save_local = var.save_local
  # ssh_user_ref - (optional) is a type of string
  ssh_user_ref = var.ssh_user_ref
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # upload_to_remote_host - (optional) is a type of bool
  upload_to_remote_host = var.upload_to_remote_host
  # upload_to_s3 - (optional) is a type of bool
  upload_to_s3 = var.upload_to_s3
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "aws_access_key" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.aws_access_key
}

output "aws_bucket_id" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.aws_bucket_id
}

output "aws_secret_access" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.aws_secret_access
}

output "backup_file_prefix" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.backup_file_prefix
}

output "backup_passphrase" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.backup_passphrase
}

output "id" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.id
}

output "remote_directory" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.remote_directory
}

output "remote_hostname" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.remote_hostname
}

output "save_local" {
  description = "returns a bool"
  value       = avi_backupconfiguration.this.save_local
}

output "ssh_user_ref" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.ssh_user_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.tenant_ref
}

output "upload_to_remote_host" {
  description = "returns a bool"
  value       = avi_backupconfiguration.this.upload_to_remote_host
}

output "upload_to_s3" {
  description = "returns a bool"
  value       = avi_backupconfiguration.this.upload_to_s3
}

output "uuid" {
  description = "returns a string"
  value       = avi_backupconfiguration.this.uuid
}

output "this" {
  value = avi_backupconfiguration.this
}
```

[top](#index)