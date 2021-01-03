# checkpoint_management_backup_domain

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
module "checkpoint_management_backup_domain" {
  source = "./modules/checkpoint/r/checkpoint_management_backup_domain"

  # domain - (required) is a type of string
  domain = null
  # file_path - (optional) is a type of string
  file_path = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - Domain can be identified by name or UID."
  type        = string
}

variable "file_path" {
  description = "(optional) - Path in which the backup domain data will be saved. <br>Should be the directory path or the full file path with \".tgz\" <br>If no path was inserted the default will be: \"/var/log/&lt;domain name&gt;_&lt;date&gt;.tgz\"."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_backup_domain" "this" {
  domain    = var.domain
  file_path = var.file_path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_backup_domain.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_backup_domain.this.task_id
}

output "this" {
  value = checkpoint_management_backup_domain.this
}
```

[top](#index)