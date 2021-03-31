# checkpoint_management_get_attachment

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
module "checkpoint_management_get_attachment" {
  source = "./modules/checkpoint/r/checkpoint_management_get_attachment"

  # attachment_id - (optional) is a type of string
  attachment_id = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "attachment_id" {
  description = "(optional) - Attachment identifier from a log record."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Log uid from a log record."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_get_attachment" "this" {
  attachment_id = var.attachment_id
  uid           = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_get_attachment.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_get_attachment.this.task_id
}

output "this" {
  value = checkpoint_management_get_attachment.this
}
```

[top](#index)