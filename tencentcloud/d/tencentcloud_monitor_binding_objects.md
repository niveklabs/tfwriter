# tencentcloud_monitor_binding_objects

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
module "tencentcloud_monitor_binding_objects" {
  source = "./modules/tencentcloud/d/tencentcloud_monitor_binding_objects"

  # group_id - (required) is a type of number
  group_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - Policy group ID for query."
  type        = number
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_monitor_binding_objects" "this" {
  # group_id - (required) is a type of number
  group_id = var.group_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_monitor_binding_objects.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_monitor_binding_objects.this.list
}

output "this" {
  value = tencentcloud_monitor_binding_objects.this
}
```

[top](#index)