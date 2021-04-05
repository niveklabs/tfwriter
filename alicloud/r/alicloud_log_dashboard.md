# alicloud_log_dashboard

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
module "alicloud_log_dashboard" {
  source = "./modules/alicloud/r/alicloud_log_dashboard"

  # char_list - (required) is a type of string
  char_list = null
  # dashboard_name - (required) is a type of string
  dashboard_name = null
  # display_name - (optional) is a type of string
  display_name = null
  # project_name - (required) is a type of string
  project_name = null
}
```

[top](#index)

### Variables

```terraform
variable "char_list" {
  description = "(required)"
  type        = string
}

variable "dashboard_name" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_log_dashboard" "this" {
  char_list      = var.char_list
  dashboard_name = var.dashboard_name
  display_name   = var.display_name
  project_name   = var.project_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_log_dashboard.this.id
}

output "this" {
  value = alicloud_log_dashboard.this
}
```

[top](#index)