# checkpoint_management_verify_software_package

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
module "checkpoint_management_verify_software_package" {
  source = "./modules/checkpoint/r/checkpoint_management_verify_software_package"

  # concurrency_limit - (optional) is a type of number
  concurrency_limit = null
  # name - (required) is a type of string
  name = null
  # targets - (required) is a type of set of string
  targets = []
}
```

[top](#index)

### Variables

```terraform
variable "concurrency_limit" {
  description = "(optional) - The number of targets, on which the same package is installed at the same time."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of the software package."
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
resource "checkpoint_management_verify_software_package" "this" {
  concurrency_limit = var.concurrency_limit
  name              = var.name
  targets           = var.targets
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_verify_software_package.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_verify_software_package.this.task_id
}

output "this" {
  value = checkpoint_management_verify_software_package.this
}
```

[top](#index)