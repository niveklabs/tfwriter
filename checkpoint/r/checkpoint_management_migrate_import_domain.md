# checkpoint_management_migrate_import_domain

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
module "checkpoint_management_migrate_import_domain" {
  source = "./modules/checkpoint/r/checkpoint_management_migrate_import_domain"

  # domain_ip_address - (required) is a type of string
  domain_ip_address = null
  # domain_name - (required) is a type of string
  domain_name = null
  # domain_server_name - (required) is a type of string
  domain_server_name = null
  # file_path - (required) is a type of string
  file_path = null
  # include_logs - (optional) is a type of bool
  include_logs = null
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
  description = "(required) - Path to the exported file to be imported. <br>Should be the full file path (example, \"/var/log/domain1_exported.tgz\")."
  type        = string
}

variable "include_logs" {
  description = "(optional) - Import logs from the input package."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_migrate_import_domain" "this" {
  domain_ip_address  = var.domain_ip_address
  domain_name        = var.domain_name
  domain_server_name = var.domain_server_name
  file_path          = var.file_path
  include_logs       = var.include_logs
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_migrate_import_domain.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_migrate_import_domain.this.task_id
}

output "this" {
  value = checkpoint_management_migrate_import_domain.this
}
```

[top](#index)