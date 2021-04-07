# alicloud_ess_scalinggroup_vserver_groups

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
module "alicloud_ess_scalinggroup_vserver_groups" {
  source = "./modules/alicloud/r/alicloud_ess_scalinggroup_vserver_groups"

  # force - (optional) is a type of bool
  force = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null

  vserver_groups = [{
    loadbalancer_id = null
    vserver_attributes = [{
      port             = null
      vserver_group_id = null
      weight           = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}

variable "vserver_groups" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      loadbalancer_id = string
      vserver_attributes = set(object(
        {
          port             = number
          vserver_group_id = string
          weight           = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_scalinggroup_vserver_groups" "this" {
  # force - (optional) is a type of bool
  force = var.force
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id

  dynamic "vserver_groups" {
    for_each = var.vserver_groups
    content {
      # loadbalancer_id - (required) is a type of string
      loadbalancer_id = vserver_groups.value["loadbalancer_id"]

      dynamic "vserver_attributes" {
        for_each = vserver_groups.value.vserver_attributes
        content {
          # port - (required) is a type of number
          port = vserver_attributes.value["port"]
          # vserver_group_id - (required) is a type of string
          vserver_group_id = vserver_attributes.value["vserver_group_id"]
          # weight - (required) is a type of number
          weight = vserver_attributes.value["weight"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ess_scalinggroup_vserver_groups.this.id
}

output "this" {
  value = alicloud_ess_scalinggroup_vserver_groups.this
}
```

[top](#index)