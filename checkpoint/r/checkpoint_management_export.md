# checkpoint_management_export

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
module "checkpoint_management_export" {
  source = "./modules/checkpoint/r/checkpoint_management_export"

  # exclude_classes - (optional) is a type of set of string
  exclude_classes = []
  # exclude_topics - (optional) is a type of set of string
  exclude_topics = []
  # export_files_by_class - (optional) is a type of bool
  export_files_by_class = null
  # include_classes - (optional) is a type of set of string
  include_classes = []
  # include_topics - (optional) is a type of set of string
  include_topics = []
  # query_limit - (optional) is a type of number
  query_limit = null
}
```

[top](#index)

### Variables

```terraform
variable "exclude_classes" {
  description = "(optional) - N/A"
  type        = set(string)
  default     = null
}

variable "exclude_topics" {
  description = "(optional) - N/A"
  type        = set(string)
  default     = null
}

variable "export_files_by_class" {
  description = "(optional) - N/A"
  type        = bool
  default     = null
}

variable "include_classes" {
  description = "(optional) - N/A"
  type        = set(string)
  default     = null
}

variable "include_topics" {
  description = "(optional) - N/A"
  type        = set(string)
  default     = null
}

variable "query_limit" {
  description = "(optional) - N/A"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_export" "this" {
  exclude_classes       = var.exclude_classes
  exclude_topics        = var.exclude_topics
  export_files_by_class = var.export_files_by_class
  include_classes       = var.include_classes
  include_topics        = var.include_topics
  query_limit           = var.query_limit
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_export.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_export.this.task_id
}

output "this" {
  value = checkpoint_management_export.this
}
```

[top](#index)