# alicloud_cms_site_monitor

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
module "alicloud_cms_site_monitor" {
  source = "./modules/alicloud/r/alicloud_cms_site_monitor"

  # address - (required) is a type of string
  address = null
  # alert_ids - (optional) is a type of list of string
  alert_ids = []
  # interval - (optional) is a type of number
  interval = null
  # options_json - (optional) is a type of string
  options_json = null
  # task_name - (required) is a type of string
  task_name = null
  # task_type - (required) is a type of string
  task_type = null

  isp_cities = [{
    city = null
    isp  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "alert_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "options_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "task_name" {
  description = "(required)"
  type        = string
}

variable "task_type" {
  description = "(required)"
  type        = string
}

variable "isp_cities" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      city = string
      isp  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cms_site_monitor" "this" {
  address      = var.address
  alert_ids    = var.alert_ids
  interval     = var.interval
  options_json = var.options_json
  task_name    = var.task_name
  task_type    = var.task_type

  dynamic "isp_cities" {
    for_each = var.isp_cities
    content {
      city = isp_cities.value["city"]
      isp  = isp_cities.value["isp"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = alicloud_cms_site_monitor.this.create_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_cms_site_monitor.this.id
}

output "task_state" {
  description = "returns a string"
  value       = alicloud_cms_site_monitor.this.task_state
}

output "update_time" {
  description = "returns a string"
  value       = alicloud_cms_site_monitor.this.update_time
}

output "this" {
  value = alicloud_cms_site_monitor.this
}
```

[top](#index)