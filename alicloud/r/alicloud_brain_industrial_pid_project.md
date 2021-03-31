# alicloud_brain_industrial_pid_project

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "alicloud_brain_industrial_pid_project" {
  source = "./modules/alicloud/r/alicloud_brain_industrial_pid_project"

  # pid_organization_id - (required) is a type of string
  pid_organization_id = null
  # pid_project_desc - (optional) is a type of string
  pid_project_desc = null
  # pid_project_name - (required) is a type of string
  pid_project_name = null
}
```

[top](#index)

### Variables

```terraform
variable "pid_organization_id" {
  description = "(required)"
  type        = string
}

variable "pid_project_desc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pid_project_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_brain_industrial_pid_project" "this" {
  pid_organization_id = var.pid_organization_id
  pid_project_desc    = var.pid_project_desc
  pid_project_name    = var.pid_project_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_brain_industrial_pid_project.this.id
}

output "this" {
  value = alicloud_brain_industrial_pid_project.this
}
```

[top](#index)