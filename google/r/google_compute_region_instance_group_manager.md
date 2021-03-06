# google_compute_region_instance_group_manager

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_region_instance_group_manager" {
  source = "./modules/google/r/google_compute_region_instance_group_manager"

  # base_instance_name - (required) is a type of string
  base_instance_name = null
  # description - (optional) is a type of string
  description = null
  # distribution_policy_target_shape - (optional) is a type of string
  distribution_policy_target_shape = null
  # distribution_policy_zones - (optional) is a type of set of string
  distribution_policy_zones = []
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # target_pools - (optional) is a type of set of string
  target_pools = []
  # target_size - (optional) is a type of number
  target_size = null
  # wait_for_instances - (optional) is a type of bool
  wait_for_instances = null

  auto_healing_policies = [{
    health_check      = null
    initial_delay_sec = null
  }]

  named_port = [{
    name = null
    port = null
  }]

  stateful_disk = [{
    delete_rule = null
    device_name = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  update_policy = [{
    instance_redistribution_type = null
    max_surge_fixed              = null
    max_surge_percent            = null
    max_unavailable_fixed        = null
    max_unavailable_percent      = null
    min_ready_sec                = null
    minimal_action               = null
    replacement_method           = null
    type                         = null
  }]

  version = [{
    instance_template = null
    name              = null
    target_size = [{
      fixed   = null
      percent = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_instance_name" {
  description = "(required) - The base instance name to use for instances in this group. The value must be a valid RFC1035 name. Supported characters are lowercase letters, numbers, and hyphens (-). Instances are named by appending a hyphen and a random four-character string to the base instance name."
  type        = string
}

variable "description" {
  description = "(optional) - An optional textual description of the instance group manager."
  type        = string
  default     = null
}

variable "distribution_policy_target_shape" {
  description = "(optional) - The shape to which the group converges either proactively or on resize events (depending on the value set in updatePolicy.instanceRedistributionType)."
  type        = string
  default     = null
}

variable "distribution_policy_zones" {
  description = "(optional) - The distribution policy for this managed instance group. You can specify one or more values."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The name of the instance group manager. Must be 1-63 characters long and comply with RFC1035. Supported characters include lowercase letters, numbers, and hyphens."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region where the managed instance group resides."
  type        = string
  default     = null
}

variable "target_pools" {
  description = "(optional) - The full URL of all target pools to which new instances in the group are added. Updating the target pools attribute does not affect existing instances."
  type        = set(string)
  default     = null
}

variable "target_size" {
  description = "(optional) - The target number of running instances for this managed instance group. This value should always be explicitly set unless this resource is attached to an autoscaler, in which case it should never be set. Defaults to 0."
  type        = number
  default     = null
}

variable "wait_for_instances" {
  description = "(optional) - Whether to wait for all instances to be created/updated before returning. Note that if this is set to true and the operation does not succeed, Terraform will continue trying until it times out."
  type        = bool
  default     = null
}

variable "auto_healing_policies" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      health_check      = string
      initial_delay_sec = number
    }
  ))
  default = []
}

variable "named_port" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      port = number
    }
  ))
  default = []
}

variable "stateful_disk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      delete_rule = string
      device_name = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "update_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instance_redistribution_type = string
      max_surge_fixed              = number
      max_surge_percent            = number
      max_unavailable_fixed        = number
      max_unavailable_percent      = number
      min_ready_sec                = number
      minimal_action               = string
      replacement_method           = string
      type                         = string
    }
  ))
  default = []
}

variable "version" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      instance_template = string
      name              = string
      target_size = list(object(
        {
          fixed   = number
          percent = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_region_instance_group_manager" "this" {
  # base_instance_name - (required) is a type of string
  base_instance_name = var.base_instance_name
  # description - (optional) is a type of string
  description = var.description
  # distribution_policy_target_shape - (optional) is a type of string
  distribution_policy_target_shape = var.distribution_policy_target_shape
  # distribution_policy_zones - (optional) is a type of set of string
  distribution_policy_zones = var.distribution_policy_zones
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # target_pools - (optional) is a type of set of string
  target_pools = var.target_pools
  # target_size - (optional) is a type of number
  target_size = var.target_size
  # wait_for_instances - (optional) is a type of bool
  wait_for_instances = var.wait_for_instances

  dynamic "auto_healing_policies" {
    for_each = var.auto_healing_policies
    content {
      # health_check - (required) is a type of string
      health_check = auto_healing_policies.value["health_check"]
      # initial_delay_sec - (required) is a type of number
      initial_delay_sec = auto_healing_policies.value["initial_delay_sec"]
    }
  }

  dynamic "named_port" {
    for_each = var.named_port
    content {
      # name - (required) is a type of string
      name = named_port.value["name"]
      # port - (required) is a type of number
      port = named_port.value["port"]
    }
  }

  dynamic "stateful_disk" {
    for_each = var.stateful_disk
    content {
      # delete_rule - (optional) is a type of string
      delete_rule = stateful_disk.value["delete_rule"]
      # device_name - (required) is a type of string
      device_name = stateful_disk.value["device_name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "update_policy" {
    for_each = var.update_policy
    content {
      # instance_redistribution_type - (optional) is a type of string
      instance_redistribution_type = update_policy.value["instance_redistribution_type"]
      # max_surge_fixed - (optional) is a type of number
      max_surge_fixed = update_policy.value["max_surge_fixed"]
      # max_surge_percent - (optional) is a type of number
      max_surge_percent = update_policy.value["max_surge_percent"]
      # max_unavailable_fixed - (optional) is a type of number
      max_unavailable_fixed = update_policy.value["max_unavailable_fixed"]
      # max_unavailable_percent - (optional) is a type of number
      max_unavailable_percent = update_policy.value["max_unavailable_percent"]
      # min_ready_sec - (optional) is a type of number
      min_ready_sec = update_policy.value["min_ready_sec"]
      # minimal_action - (required) is a type of string
      minimal_action = update_policy.value["minimal_action"]
      # replacement_method - (optional) is a type of string
      replacement_method = update_policy.value["replacement_method"]
      # type - (required) is a type of string
      type = update_policy.value["type"]
    }
  }

  dynamic "version" {
    for_each = var.version
    content {
      # instance_template - (required) is a type of string
      instance_template = version.value["instance_template"]
      # name - (optional) is a type of string
      name = version.value["name"]

      dynamic "target_size" {
        for_each = version.value.target_size
        content {
          # fixed - (optional) is a type of number
          fixed = target_size.value["fixed"]
          # percent - (optional) is a type of number
          percent = target_size.value["percent"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "distribution_policy_target_shape" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.distribution_policy_target_shape
}

output "distribution_policy_zones" {
  description = "returns a set of string"
  value       = google_compute_region_instance_group_manager.this.distribution_policy_zones
}

output "fingerprint" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.id
}

output "instance_group" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.instance_group
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_region_instance_group_manager.this.self_link
}

output "target_size" {
  description = "returns a number"
  value       = google_compute_region_instance_group_manager.this.target_size
}

output "this" {
  value = google_compute_region_instance_group_manager.this
}
```

[top](#index)