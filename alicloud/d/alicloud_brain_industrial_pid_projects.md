# alicloud_brain_industrial_pid_projects

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_brain_industrial_pid_projects" {
  source = "./modules/alicloud/d/alicloud_brain_industrial_pid_projects"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # pid_organization_id - (optional) is a type of string
  pid_organization_id = null
  # pid_project_name - (optional) is a type of string
  pid_project_name = null
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

variable "pid_organization_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pid_project_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_brain_industrial_pid_projects" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # pid_organization_id - (optional) is a type of string
  pid_organization_id = var.pid_organization_id
  # pid_project_name - (optional) is a type of string
  pid_project_name = var.pid_project_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_brain_industrial_pid_projects.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_brain_industrial_pid_projects.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_brain_industrial_pid_projects.this.names
}

output "projects" {
  description = "returns a list of object"
  value       = data.alicloud_brain_industrial_pid_projects.this.projects
}

output "this" {
  value = alicloud_brain_industrial_pid_projects.this
}
```

[top](#index)