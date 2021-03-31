# checkpoint_management_run_ips_update

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
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_run_ips_update" {
  source = "./modules/checkpoint/r/checkpoint_management_run_ips_update"

  # package_path - (optional) is a type of string
  package_path = null
}
```

[top](#index)

### Variables

```terraform
variable "package_path" {
  description = "(optional) - Offline update package path."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_run_ips_update" "this" {
  package_path = var.package_path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_run_ips_update.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_run_ips_update.this.task_id
}

output "this" {
  value = checkpoint_management_run_ips_update.this
}
```

[top](#index)