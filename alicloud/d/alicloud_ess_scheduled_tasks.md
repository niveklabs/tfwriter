# alicloud_ess_scheduled_tasks

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ess_scheduled_tasks" {
  source = "./modules/alicloud/d/alicloud_ess_scheduled_tasks"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # scheduled_action - (optional) is a type of string
  scheduled_action = null
  # scheduled_task_id - (optional) is a type of string
  scheduled_task_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduled_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduled_task_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ess_scheduled_tasks" "this" {
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  scheduled_action  = var.scheduled_action
  scheduled_task_id = var.scheduled_task_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ess_scheduled_tasks.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ess_scheduled_tasks.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ess_scheduled_tasks.this.names
}

output "tasks" {
  description = "returns a list of object"
  value       = data.alicloud_ess_scheduled_tasks.this.tasks
}

output "this" {
  value = alicloud_ess_scheduled_tasks.this
}
```

[top](#index)