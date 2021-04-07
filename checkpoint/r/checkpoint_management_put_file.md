# checkpoint_management_put_file

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
module "checkpoint_management_put_file" {
  source = "./modules/checkpoint/r/checkpoint_management_put_file"

  # comments - (optional) is a type of string
  comments = null
  # file_content - (optional) is a type of string
  file_content = null
  # file_name - (optional) is a type of string
  file_name = null
  # file_path - (optional) is a type of string
  file_path = null
  # targets - (required) is a type of set of string
  targets = []
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "file_content" {
  description = "(optional) - Text file content."
  type        = string
  default     = null
}

variable "file_name" {
  description = "(optional) - Text file name."
  type        = string
  default     = null
}

variable "file_path" {
  description = "(optional) - Text file target path."
  type        = string
  default     = null
}

variable "targets" {
  description = "(required) - On what targets to execute this command. Targets may be identified by their name, or object unique identifier."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_put_file" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # file_content - (optional) is a type of string
  file_content = var.file_content
  # file_name - (optional) is a type of string
  file_name = var.file_name
  # file_path - (optional) is a type of string
  file_path = var.file_path
  # targets - (required) is a type of set of string
  targets = var.targets
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_put_file.this.id
}

output "tasks" {
  description = "returns a set of string"
  value       = checkpoint_management_put_file.this.tasks
}

output "this" {
  value = checkpoint_management_put_file.this
}
```

[top](#index)