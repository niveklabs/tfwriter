# checkpoint_management_run_script

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
module "checkpoint_management_run_script" {
  source = "./modules/checkpoint/r/checkpoint_management_run_script"

  # args - (optional) is a type of string
  args = null
  # comments - (optional) is a type of string
  comments = null
  # script - (required) is a type of string
  script = null
  # script_name - (required) is a type of string
  script_name = null
  # targets - (required) is a type of set of string
  targets = []
}
```

[top](#index)

### Variables

```terraform
variable "args" {
  description = "(optional) - Script arguments."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "script" {
  description = "(required) - Script body."
  type        = string
}

variable "script_name" {
  description = "(required) - Script name."
  type        = string
}

variable "targets" {
  description = "(required) - On what targets to execute this command. Targets may be identified by their name, or object unique identifier."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_run_script" "this" {
  args        = var.args
  comments    = var.comments
  script      = var.script
  script_name = var.script_name
  targets     = var.targets
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_run_script.this.id
}

output "tasks" {
  description = "returns a set of string"
  value       = checkpoint_management_run_script.this.tasks
}

output "this" {
  value = checkpoint_management_run_script.this
}
```

[top](#index)