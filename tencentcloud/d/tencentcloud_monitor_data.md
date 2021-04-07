# tencentcloud_monitor_data

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_monitor_data" {
  source = "./modules/tencentcloud/d/tencentcloud_monitor_data"

  # end_time - (required) is a type of string
  end_time = null
  # metric_name - (required) is a type of string
  metric_name = null
  # namespace - (required) is a type of string
  namespace = null
  # period - (optional) is a type of number
  period = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # start_time - (required) is a type of string
  start_time = null

  dimensions = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "end_time" {
  description = "(required) - End time for this query, eg:`2018-09-22T20:00:00+08:00`."
  type        = string
}

variable "metric_name" {
  description = "(required) - Metric name, please refer to the documentation of monitor interface of each product."
  type        = string
}

variable "namespace" {
  description = "(required) - Namespace of each cloud product in monitor system, refer to `data.tencentcloud_monitor_product_namespace`."
  type        = string
}

variable "period" {
  description = "(optional) - Statistical period."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "start_time" {
  description = "(required) - Start time for this query, eg:`2018-09-22T19:51:23+08:00`."
  type        = string
}

variable "dimensions" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_monitor_data" "this" {
  end_time           = var.end_time
  metric_name        = var.metric_name
  namespace          = var.namespace
  period             = var.period
  result_output_file = var.result_output_file
  start_time         = var.start_time

  dynamic "dimensions" {
    for_each = var.dimensions
    content {
      name  = dimensions.value["name"]
      value = dimensions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_monitor_data.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_monitor_data.this.list
}

output "this" {
  value = tencentcloud_monitor_data.this
}
```

[top](#index)