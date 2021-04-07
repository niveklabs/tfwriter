# tencentcloud_monitor_binding_object

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_monitor_binding_object" {
  source = "./modules/tencentcloud/r/tencentcloud_monitor_binding_object"

  # group_id - (required) is a type of number
  group_id = null

  dimensions = [{
    dimensions_json = null
    unique_id       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - Policy group ID for binding objects."
  type        = number
}

variable "dimensions" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      dimensions_json = string
      unique_id       = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_monitor_binding_object" "this" {
  # group_id - (required) is a type of number
  group_id = var.group_id

  dynamic "dimensions" {
    for_each = var.dimensions
    content {
      # dimensions_json - (required) is a type of string
      dimensions_json = dimensions.value["dimensions_json"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_monitor_binding_object.this.id
}

output "this" {
  value = tencentcloud_monitor_binding_object.this
}
```

[top](#index)