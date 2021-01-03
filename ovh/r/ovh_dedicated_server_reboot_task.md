# ovh_dedicated_server_reboot_task

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_dedicated_server_reboot_task" {
  source = "./modules/ovh/r/ovh_dedicated_server_reboot_task"

  # keepers - (required) is a type of list of string
  keepers = []
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "keepers" {
  description = "(required) - Change this value to recreate a reboot task."
  type        = list(string)
}

variable "service_name" {
  description = "(required) - The internal name of your dedicated server."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_dedicated_server_reboot_task" "this" {
  keepers      = var.keepers
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.comment
}

output "done_date" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.done_date
}

output "function" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.function
}

output "id" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.id
}

output "last_update" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.last_update
}

output "start_date" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.start_date
}

output "status" {
  description = "returns a string"
  value       = ovh_dedicated_server_reboot_task.this.status
}

output "this" {
  value = ovh_dedicated_server_reboot_task.this
}
```

[top](#index)