# checkpoint_management_restore_domain

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_restore_domain" {
  source = "./modules/checkpoint/r/checkpoint_management_restore_domain"

  # domain_ip_address - (required) is a type of string
  domain_ip_address = null
  # domain_name - (required) is a type of string
  domain_name = null
  # domain_server_name - (required) is a type of string
  domain_server_name = null
  # file_path - (required) is a type of string
  file_path = null
  # verify_only - (optional) is a type of bool
  verify_only = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_ip_address" {
  description = "(required) - IPv4 address.<br><font color=\"red\">Required only for</font> importing Security Management Server into Multi-Domain Server."
  type        = string
}

variable "domain_name" {
  description = "(required) - Domain name. Should be unique in the MDS.<br><font color=\"red\">Required only for</font> importing Security Management Server into Multi-Domain Server."
  type        = string
}

variable "domain_server_name" {
  description = "(required) - Multi Domain server name.<br><font color=\"red\">Required only for</font> importing Security Management Server into Multi-Domain Server."
  type        = string
}

variable "file_path" {
  description = "(required) - Path to the backup file to be restored. <br>Should be the full file path (example, \"/var/log/domain1_backup.tgz\")."
  type        = string
}

variable "verify_only" {
  description = "(optional) - If true, verify that the import operation is valid for this input file and this environment <br>Note: Restore operation will not be executed."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_restore_domain" "this" {
  domain_ip_address  = var.domain_ip_address
  domain_name        = var.domain_name
  domain_server_name = var.domain_server_name
  file_path          = var.file_path
  verify_only        = var.verify_only
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_restore_domain.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_restore_domain.this.task_id
}

output "this" {
  value = checkpoint_management_restore_domain.this
}
```

[top](#index)