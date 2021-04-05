# spotinst_ocean_gke_launch_spec

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
module "spotinst_ocean_gke_launch_spec" {
  source = "./modules/spotinst/r/spotinst_ocean_gke_launch_spec"

  # ocean_id - (required) is a type of string
  ocean_id = null
  # source_image - (required) is a type of string
  source_image = null

  autoscale_headrooms = [{
    cpu_per_unit    = null
    gpu_per_unit    = null
    memory_per_unit = null
    num_of_units    = null
  }]

  labels = [{
    key   = null
    value = null
  }]

  metadata = [{
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
variable "ocean_id" {
  description = "(required)"
  type        = string
}

variable "source_image" {
  description = "(required)"
  type        = string
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

variable "metadata" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
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
resource "spotinst_ocean_gke_launch_spec" "this" {
  ocean_id     = var.ocean_id
  source_image = var.source_image

  dynamic "autoscale_headrooms" {
    for_each = var.autoscale_headrooms
    content {
      cpu_per_unit    = autoscale_headrooms.value["cpu_per_unit"]
      gpu_per_unit    = autoscale_headrooms.value["gpu_per_unit"]
      memory_per_unit = autoscale_headrooms.value["memory_per_unit"]
      num_of_units    = autoscale_headrooms.value["num_of_units"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      key   = labels.value["key"]
      value = labels.value["value"]
    }
  }

  dynamic "metadata" {
    for_each = var.metadata
    content {
      key   = metadata.value["key"]
      value = metadata.value["value"]
    }
  }

  dynamic "taints" {
    for_each = var.taints
    content {
      effect = taints.value["effect"]
      key    = taints.value["key"]
      value  = taints.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_ocean_gke_launch_spec.this.id
}

output "this" {
  value = spotinst_ocean_gke_launch_spec.this
}
```

[top](#index)