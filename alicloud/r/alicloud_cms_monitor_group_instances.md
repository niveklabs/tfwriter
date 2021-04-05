# alicloud_cms_monitor_group_instances

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
module "alicloud_cms_monitor_group_instances" {
  source = "./modules/alicloud/r/alicloud_cms_monitor_group_instances"

  # group_id - (required) is a type of string
  group_id = null

  instances = [{
    category      = null
    instance_id   = null
    instance_name = null
    region_id     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required)"
  type        = string
}

variable "instances" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      category      = string
      instance_id   = string
      instance_name = string
      region_id     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cms_monitor_group_instances" "this" {
  group_id = var.group_id

  dynamic "instances" {
    for_each = var.instances
    content {
      category      = instances.value["category"]
      instance_id   = instances.value["instance_id"]
      instance_name = instances.value["instance_name"]
      region_id     = instances.value["region_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cms_monitor_group_instances.this.id
}

output "this" {
  value = alicloud_cms_monitor_group_instances.this
}
```

[top](#index)