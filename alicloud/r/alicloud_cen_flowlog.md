# alicloud_cen_flowlog

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
module "alicloud_cen_flowlog" {
  source = "./modules/alicloud/r/alicloud_cen_flowlog"

  # cen_id - (required) is a type of string
  cen_id = null
  # description - (optional) is a type of string
  description = null
  # flow_log_name - (optional) is a type of string
  flow_log_name = null
  # log_store_name - (required) is a type of string
  log_store_name = null
  # project_name - (required) is a type of string
  project_name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_log_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_store_name" {
  description = "(required)"
  type        = string
}

variable "project_name" {
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

### Resource

```terraform
resource "alicloud_cen_flowlog" "this" {
  # cen_id - (required) is a type of string
  cen_id = var.cen_id
  # description - (optional) is a type of string
  description = var.description
  # flow_log_name - (optional) is a type of string
  flow_log_name = var.flow_log_name
  # log_store_name - (required) is a type of string
  log_store_name = var.log_store_name
  # project_name - (required) is a type of string
  project_name = var.project_name
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cen_flowlog.this.id
}

output "this" {
  value = alicloud_cen_flowlog.this
}
```

[top](#index)