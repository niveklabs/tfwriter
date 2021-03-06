# alicloud_log_machine_group

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_log_machine_group" {
  source = "./modules/alicloud/r/alicloud_log_machine_group"

  # identify_list - (required) is a type of set of string
  identify_list = []
  # identify_type - (optional) is a type of string
  identify_type = null
  # name - (required) is a type of string
  name = null
  # project - (required) is a type of string
  project = null
  # topic - (optional) is a type of string
  topic = null
}
```

[top](#index)

### Variables

```terraform
variable "identify_list" {
  description = "(required)"
  type        = set(string)
}

variable "identify_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "topic" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_log_machine_group" "this" {
  # identify_list - (required) is a type of set of string
  identify_list = var.identify_list
  # identify_type - (optional) is a type of string
  identify_type = var.identify_type
  # name - (required) is a type of string
  name = var.name
  # project - (required) is a type of string
  project = var.project
  # topic - (optional) is a type of string
  topic = var.topic
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_log_machine_group.this.id
}

output "this" {
  value = alicloud_log_machine_group.this
}
```

[top](#index)