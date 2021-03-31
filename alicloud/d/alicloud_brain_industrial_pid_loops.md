# alicloud_brain_industrial_pid_loops

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
module "alicloud_brain_industrial_pid_loops" {
  source = "./modules/alicloud/d/alicloud_brain_industrial_pid_loops"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # pid_loop_name - (optional) is a type of string
  pid_loop_name = null
  # pid_project_id - (required) is a type of string
  pid_project_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "pid_loop_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pid_project_id" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_brain_industrial_pid_loops" "this" {
  enable_details = var.enable_details
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
  pid_loop_name  = var.pid_loop_name
  pid_project_id = var.pid_project_id
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_brain_industrial_pid_loops.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_brain_industrial_pid_loops.this.ids
}

output "loops" {
  description = "returns a list of object"
  value       = data.alicloud_brain_industrial_pid_loops.this.loops
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_brain_industrial_pid_loops.this.names
}

output "this" {
  value = alicloud_brain_industrial_pid_loops.this
}
```

[top](#index)