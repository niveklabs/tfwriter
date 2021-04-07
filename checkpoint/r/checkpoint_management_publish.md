# checkpoint_management_publish

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
module "checkpoint_management_publish" {
  source = "./modules/checkpoint/r/checkpoint_management_publish"

  # triggers - (optional) is a type of set of string
  triggers = []
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "triggers" {
  description = "(optional) - Triggers a publish if there are any changes to objects in this list."
  type        = set(string)
  default     = null
}

variable "uid" {
  description = "(optional) - Session unique identifier. Specify it to publish a different session than the one you currently use."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_publish" "this" {
  # triggers - (optional) is a type of set of string
  triggers = var.triggers
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_publish.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_publish.this.task_id
}

output "this" {
  value = checkpoint_management_publish.this
}
```

[top](#index)