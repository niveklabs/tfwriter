# spotinst_ocean_aws_launch_spec

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_ocean_aws_launch_spec" {
  source = "./modules/spotinst/r/spotinst_ocean_aws_launch_spec"

  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # image_id - (optional) is a type of string
  image_id = null
  # instance_types - (optional) is a type of list of string
  instance_types = []
  # name - (optional) is a type of string
  name = null
  # ocean_id - (required) is a type of string
  ocean_id = null
  # root_volume_size - (optional) is a type of number
  root_volume_size = null
  # security_groups - (optional) is a type of list of string
  security_groups = []
  # subnet_ids - (optional) is a type of list of string
  subnet_ids = []
  # user_data - (optional) is a type of string
  user_data = null

  autoscale_headrooms = [{
    cpu_per_unit    = null
    gpu_per_unit    = null
    memory_per_unit = null
    num_of_units    = null
  }]

  block_device_mappings = [{
    device_name = null
    ebs = [{
      delete_on_termination = null
      dynamic_volume_size = [{
        base_size              = null
        resource               = null
        size_per_resource_unit = null
      }]
      encrypted   = null
      iops        = null
      kms_key_id  = null
      snapshot_id = null
      volume_size = null
      volume_type = null
    }]
    no_device    = null
    virtual_name = null
  }]

  elastic_ip_pool = [{
    tag_selector = [{
      tag_key   = null
      tag_value = null
    }]
  }]

  labels = [{
    key   = null
    value = null
  }]

  resource_limits = [{
    max_instance_count = null
  }]

  strategy = [{
    spot_percentage = null
  }]

  tags = [{
    key   = null
    value = null
  }]

  taints = [{
    effect = null
    key    = null
    value  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "iam_instance_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocean_id" {
  description = "(required)"
  type        = string
}

variable "root_volume_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "subnet_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscale_headrooms" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cpu_per_unit    = number
      gpu_per_unit    = number
      memory_per_unit = number
      num_of_units    = number
    }
  ))
  default = []
}

variable "block_device_mappings" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      device_name = string
      ebs = list(object(
        {
          delete_on_termination = bool
          dynamic_volume_size = list(object(
            {
              base_size              = number
              resource               = string
              size_per_resource_unit = number
            }
          ))
          encrypted   = bool
          iops        = number
          kms_key_id  = string
          snapshot_id = string
          volume_size = number
          volume_type = string
        }
      ))
      no_device    = string
      virtual_name = string
    }
  ))
  default = []
}

variable "elastic_ip_pool" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      tag_selector = list(object(
        {
          tag_key   = string
          tag_value = string
        }
      ))
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "resource_limits" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      max_instance_count = number
    }
  ))
  default = []
}

variable "strategy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      spot_percentage = number
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "taints" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      effect = string
      key    = string
      value  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_ocean_aws_launch_spec" "this" {
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = var.iam_instance_profile
  # image_id - (optional) is a type of string
  image_id = var.image_id
  # instance_types - (optional) is a type of list of string
  instance_types = var.instance_types
  # name - (optional) is a type of string
  name = var.name
  # ocean_id - (required) is a type of string
  ocean_id = var.ocean_id
  # root_volume_size - (optional) is a type of number
  root_volume_size = var.root_volume_size
  # security_groups - (optional) is a type of list of string
  security_groups = var.security_groups
  # subnet_ids - (optional) is a type of list of string
  subnet_ids = var.subnet_ids
  # user_data - (optional) is a type of string
  user_data = var.user_data

  dynamic "autoscale_headrooms" {
    for_each = var.autoscale_headrooms
    content {
      # cpu_per_unit - (optional) is a type of number
      cpu_per_unit = autoscale_headrooms.value["cpu_per_unit"]
      # gpu_per_unit - (optional) is a type of number
      gpu_per_unit = autoscale_headrooms.value["gpu_per_unit"]
      # memory_per_unit - (optional) is a type of number
      memory_per_unit = autoscale_headrooms.value["memory_per_unit"]
      # num_of_units - (required) is a type of number
      num_of_units = autoscale_headrooms.value["num_of_units"]
    }
  }

  dynamic "block_device_mappings" {
    for_each = var.block_device_mappings
    content {
      # device_name - (required) is a type of string
      device_name = block_device_mappings.value["device_name"]
      # no_device - (optional) is a type of string
      no_device = block_device_mappings.value["no_device"]
      # virtual_name - (optional) is a type of string
      virtual_name = block_device_mappings.value["virtual_name"]

      dynamic "ebs" {
        for_each = block_device_mappings.value.ebs
        content {
          # delete_on_termination - (optional) is a type of bool
          delete_on_termination = ebs.value["delete_on_termination"]
          # encrypted - (optional) is a type of bool
          encrypted = ebs.value["encrypted"]
          # iops - (optional) is a type of number
          iops = ebs.value["iops"]
          # kms_key_id - (optional) is a type of string
          kms_key_id = ebs.value["kms_key_id"]
          # snapshot_id - (optional) is a type of string
          snapshot_id = ebs.value["snapshot_id"]
          # volume_size - (optional) is a type of number
          volume_size = ebs.value["volume_size"]
          # volume_type - (optional) is a type of string
          volume_type = ebs.value["volume_type"]

          dynamic "dynamic_volume_size" {
            for_each = ebs.value.dynamic_volume_size
            content {
              # base_size - (required) is a type of number
              base_size = dynamic_volume_size.value["base_size"]
              # resource - (required) is a type of string
              resource = dynamic_volume_size.value["resource"]
              # size_per_resource_unit - (required) is a type of number
              size_per_resource_unit = dynamic_volume_size.value["size_per_resource_unit"]
            }
          }

        }
      }

    }
  }

  dynamic "elastic_ip_pool" {
    for_each = var.elastic_ip_pool
    content {

      dynamic "tag_selector" {
        for_each = elastic_ip_pool.value.tag_selector
        content {
          # tag_key - (required) is a type of string
          tag_key = tag_selector.value["tag_key"]
          # tag_value - (optional) is a type of string
          tag_value = tag_selector.value["tag_value"]
        }
      }

    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      # key - (required) is a type of string
      key = labels.value["key"]
      # value - (required) is a type of string
      value = labels.value["value"]
    }
  }

  dynamic "resource_limits" {
    for_each = var.resource_limits
    content {
      # max_instance_count - (optional) is a type of number
      max_instance_count = resource_limits.value["max_instance_count"]
    }
  }

  dynamic "strategy" {
    for_each = var.strategy
    content {
      # spot_percentage - (optional) is a type of number
      spot_percentage = strategy.value["spot_percentage"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

  dynamic "taints" {
    for_each = var.taints
    content {
      # effect - (required) is a type of string
      effect = taints.value["effect"]
      # key - (required) is a type of string
      key = taints.value["key"]
      # value - (required) is a type of string
      value = taints.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_ocean_aws_launch_spec.this.id
}

output "this" {
  value = spotinst_ocean_aws_launch_spec.this
}
```

[top](#index)