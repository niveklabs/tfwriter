# wavefront_maintenance_window

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_maintenance_window" {
  source = "./modules/wavefront/r/wavefront_maintenance_window"

  # end_time_in_seconds - (required) is a type of number
  end_time_in_seconds = null
  # host_tag_group_host_names_group_anded - (optional) is a type of bool
  host_tag_group_host_names_group_anded = null
  # reason - (required) is a type of string
  reason = null
  # relevant_customer_tags - (optional) is a type of set of string
  relevant_customer_tags = []
  # relevant_host_names - (optional) is a type of set of string
  relevant_host_names = []
  # relevant_host_tags - (optional) is a type of set of string
  relevant_host_tags = []
  # relevant_host_tags_anded - (optional) is a type of bool
  relevant_host_tags_anded = null
  # start_time_in_seconds - (required) is a type of number
  start_time_in_seconds = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "end_time_in_seconds" {
  description = "(required)"
  type        = number
}

variable "host_tag_group_host_names_group_anded" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "reason" {
  description = "(required)"
  type        = string
}

variable "relevant_customer_tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relevant_host_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relevant_host_tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relevant_host_tags_anded" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "start_time_in_seconds" {
  description = "(required)"
  type        = number
}

variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_maintenance_window" "this" {
  # end_time_in_seconds - (required) is a type of number
  end_time_in_seconds = var.end_time_in_seconds
  # host_tag_group_host_names_group_anded - (optional) is a type of bool
  host_tag_group_host_names_group_anded = var.host_tag_group_host_names_group_anded
  # reason - (required) is a type of string
  reason = var.reason
  # relevant_customer_tags - (optional) is a type of set of string
  relevant_customer_tags = var.relevant_customer_tags
  # relevant_host_names - (optional) is a type of set of string
  relevant_host_names = var.relevant_host_names
  # relevant_host_tags - (optional) is a type of set of string
  relevant_host_tags = var.relevant_host_tags
  # relevant_host_tags_anded - (optional) is a type of bool
  relevant_host_tags_anded = var.relevant_host_tags_anded
  # start_time_in_seconds - (required) is a type of number
  start_time_in_seconds = var.start_time_in_seconds
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_maintenance_window.this.id
}

output "this" {
  value = wavefront_maintenance_window.this
}
```

[top](#index)