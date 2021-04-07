# tencentcloud_monitor_product_event

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
module "tencentcloud_monitor_product_event" {
  source = "./modules/tencentcloud/d/tencentcloud_monitor_product_event"

  # end_time - (optional) is a type of number
  end_time = null
  # event_name - (optional) is a type of list of string
  event_name = []
  # instance_id - (optional) is a type of list of string
  instance_id = []
  # is_alarm_config - (optional) is a type of number
  is_alarm_config = null
  # product_name - (optional) is a type of list of string
  product_name = []
  # project_id - (optional) is a type of list of string
  project_id = []
  # region_list - (optional) is a type of list of string
  region_list = []
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # start_time - (optional) is a type of number
  start_time = null
  # status - (optional) is a type of list of string
  status = []
  # type - (optional) is a type of list of string
  type = []

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
  description = "(optional) - End timestamp for this query, eg:`1588232111`. Default start time is `now-3000`."
  type        = number
  default     = null
}

variable "event_name" {
  description = "(optional) - Event name filtering, such as `guest_reboot` indicates that the machine restart."
  type        = list(string)
  default     = null
}

variable "instance_id" {
  description = "(optional) - Affect objects, such as `ins-19708ino`."
  type        = list(string)
  default     = null
}

variable "is_alarm_config" {
  description = "(optional) - Alarm status configuration filter, 1means configured, 0(default) means not configured."
  type        = number
  default     = null
}

variable "product_name" {
  description = "(optional) - Product type filtering, such as `cvm` for cloud server."
  type        = list(string)
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID filter."
  type        = list(string)
  default     = null
}

variable "region_list" {
  description = "(optional) - Region filter, such as `gz`."
  type        = list(string)
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "start_time" {
  description = "(optional) - Start timestamp for this query, eg:`1588230000`. Default start time is `now-3600`."
  type        = number
  default     = null
}

variable "status" {
  description = "(optional) - Event status filter, value range `-`,`alarm`,`recover`, indicating recovered, unrecovered and stateless."
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(optional) - Event type filtering, with value range `abnormal`,`status_change`, indicating state change and abnormal events."
  type        = list(string)
  default     = null
}

variable "dimensions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_monitor_product_event" "this" {
  # end_time - (optional) is a type of number
  end_time = var.end_time
  # event_name - (optional) is a type of list of string
  event_name = var.event_name
  # instance_id - (optional) is a type of list of string
  instance_id = var.instance_id
  # is_alarm_config - (optional) is a type of number
  is_alarm_config = var.is_alarm_config
  # product_name - (optional) is a type of list of string
  product_name = var.product_name
  # project_id - (optional) is a type of list of string
  project_id = var.project_id
  # region_list - (optional) is a type of list of string
  region_list = var.region_list
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # start_time - (optional) is a type of number
  start_time = var.start_time
  # status - (optional) is a type of list of string
  status = var.status
  # type - (optional) is a type of list of string
  type = var.type

  dynamic "dimensions" {
    for_each = var.dimensions
    content {
      # name - (optional) is a type of string
      name = dimensions.value["name"]
      # value - (optional) is a type of string
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
  value       = data.tencentcloud_monitor_product_event.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_monitor_product_event.this.list
}

output "this" {
  value = tencentcloud_monitor_product_event.this
}
```

[top](#index)