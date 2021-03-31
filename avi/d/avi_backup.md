# avi_backup

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
module "avi_backup" {
  source = "./modules/avi/d/avi_backup"

  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
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
data "avi_backup" "this" {
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "backup_config_ref" {
  description = "returns a string"
  value       = data.avi_backup.this.backup_config_ref
}

output "file_name" {
  description = "returns a string"
  value       = data.avi_backup.this.file_name
}

output "id" {
  description = "returns a string"
  value       = data.avi_backup.this.id
}

output "local_file_url" {
  description = "returns a string"
  value       = data.avi_backup.this.local_file_url
}

output "remote_file_url" {
  description = "returns a string"
  value       = data.avi_backup.this.remote_file_url
}

output "scheduler_ref" {
  description = "returns a string"
  value       = data.avi_backup.this.scheduler_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_backup.this.tenant_ref
}

output "timestamp" {
  description = "returns a string"
  value       = data.avi_backup.this.timestamp
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_backup.this.uuid
}

output "this" {
  value = avi_backup.this
}
```

[top](#index)