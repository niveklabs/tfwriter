# checkpoint_management_delete_threat_protections

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
module "checkpoint_management_delete_threat_protections" {
  source = "./modules/checkpoint/r/checkpoint_management_delete_threat_protections"

  # package_format - (optional) is a type of string
  package_format = null
}
```

[top](#index)

### Variables

```terraform
variable "package_format" {
  description = "(optional) - Protections package format."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_delete_threat_protections" "this" {
  package_format = var.package_format
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_delete_threat_protections.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_delete_threat_protections.this.task_id
}

output "this" {
  value = checkpoint_management_delete_threat_protections.this
}
```

[top](#index)