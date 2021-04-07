# tencentcloud_instance_types

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
module "tencentcloud_instance_types" {
  source = "./modules/tencentcloud/d/tencentcloud_instance_types"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cpu_core_count - (optional) is a type of number
  cpu_core_count = null
  # exclude_sold_out - (optional) is a type of bool
  exclude_sold_out = null
  # gpu_core_count - (optional) is a type of number
  gpu_core_count = null
  # memory_size - (optional) is a type of number
  memory_size = null
  # result_output_file - (optional) is a type of string
  result_output_file = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - The available zone that the CVM instance locates at. This field is conflict with `filter`."
  type        = string
  default     = null
}

variable "cpu_core_count" {
  description = "(optional) - The number of CPU cores of the instance."
  type        = number
  default     = null
}

variable "exclude_sold_out" {
  description = "(optional) - Indicate to filter instances types that is sold out or not, default is false."
  type        = bool
  default     = null
}

variable "gpu_core_count" {
  description = "(optional) - The number of GPU cores of the instance."
  type        = number
  default     = null
}

variable "memory_size" {
  description = "(optional) - Instance memory capacity, unit in GB."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_instance_types" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # cpu_core_count - (optional) is a type of number
  cpu_core_count = var.cpu_core_count
  # exclude_sold_out - (optional) is a type of bool
  exclude_sold_out = var.exclude_sold_out
  # gpu_core_count - (optional) is a type of number
  gpu_core_count = var.gpu_core_count
  # memory_size - (optional) is a type of number
  memory_size = var.memory_size
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_instance_types.this.id
}

output "instance_types" {
  description = "returns a list of object"
  value       = data.tencentcloud_instance_types.this.instance_types
}

output "this" {
  value = tencentcloud_instance_types.this
}
```

[top](#index)