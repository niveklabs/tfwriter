# spotinst_elastigroup_gke

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
module "spotinst_elastigroup_gke" {
  source = "./modules/spotinst/r/spotinst_elastigroup_gke"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # cluster_zone_name - (required) is a type of string
  cluster_zone_name = null
  # desired_capacity - (required) is a type of number
  desired_capacity = null
  # draining_timeout - (optional) is a type of number
  draining_timeout = null
  # fallback_to_ondemand - (optional) is a type of bool
  fallback_to_ondemand = null
  # instance_types_ondemand - (optional) is a type of string
  instance_types_ondemand = null
  # instance_types_preemptible - (optional) is a type of list of string
  instance_types_preemptible = []
  # ip_forwarding - (optional) is a type of bool
  ip_forwarding = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # node_image - (optional) is a type of string
  node_image = null
  # ondemand_count - (optional) is a type of number
  ondemand_count = null
  # preemptible_percentage - (optional) is a type of number
  preemptible_percentage = null
  # service_account - (optional) is a type of string
  service_account = null
  # shutdown_script - (optional) is a type of string
  shutdown_script = null
  # startup_script - (optional) is a type of string
  startup_script = null
  # tags - (optional) is a type of list of string
  tags = []

  backend_services = [{
    location_type = null
    named_ports = [{
      name  = null
      ports = []
    }]
    scheme       = null
    service_name = null
  }]

  disk = [{
    auto_delete = null
    boot        = null
    device_name = null
    initialize_params = [{
      disk_size_gb = null
      disk_type    = null
      source_image = null
    }]
    interface = null
    mode      = null
    source    = null
    type      = null
  }]

  gpu = [{
    count = null
    type  = null
  }]

  instance_types_custom = [{
    memory_gib = null
    vcpu       = null
  }]

  integration_docker_swarm = [{
    master_host = null
    master_port = null
  }]

  integration_gke = [{
    auto_update        = null
    autoscale_cooldown = null
    autoscale_down = [{
      evaluation_periods = null
    }]
    autoscale_headroom = [{
      cpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    autoscale_is_auto_config = null
    autoscale_is_enabled     = null
    autoscale_labels = [{
      key   = null
      value = null
    }]
    cluster_id = null
    location   = null
  }]

  labels = [{
    key   = null
    value = null
  }]

  metadata = [{
    key   = null
    value = null
  }]

  network_interface = [{
    access_configs = [{
      name = null
      type = null
    }]
    alias_ip_ranges = [{
      ip_cidr_range         = null
      subnetwork_range_name = null
    }]
    network = null
  }]

  scaling_down_policy = [{
    action_type = null
    adjustment  = null
    cooldown    = null
    dimensions = [{
      name  = null
      value = null
    }]
    evaluation_periods = null
    metric_name        = null
    namespace          = null
    operator           = null
    period             = null
    policy_name        = null
    source             = null
    statistic          = null
    threshold          = null
    unit               = null
  }]

  scaling_up_policy = [{
    action_type = null
    adjustment  = null
    cooldown    = null
    dimensions = [{
      name  = null
      value = null
    }]
    evaluation_periods = null
    metric_name        = null
    namespace          = null
    operator           = null
    period             = null
    policy_name        = null
    source             = null
    statistic          = null
    threshold          = null
    unit               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_zone_name" {
  description = "(required)"
  type        = string
}

variable "desired_capacity" {
  description = "(required)"
  type        = number
}

variable "draining_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fallback_to_ondemand" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_types_ondemand" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_types_preemptible" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ip_forwarding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ondemand_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preemptible_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shutdown_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "startup_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "backend_services" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      location_type = string
      named_ports = set(object(
        {
          name  = string
          ports = list(string)
        }
      ))
      scheme       = string
      service_name = string
    }
  ))
  default = []
}

variable "disk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auto_delete = bool
      boot        = bool
      device_name = string
      initialize_params = set(object(
        {
          disk_size_gb = string
          disk_type    = string
          source_image = string
        }
      ))
      interface = string
      mode      = string
      source    = string
      type      = string
    }
  ))
  default = []
}

variable "gpu" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      count = number
      type  = string
    }
  ))
  default = []
}

variable "instance_types_custom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      memory_gib = number
      vcpu       = number
    }
  ))
  default = []
}

variable "integration_docker_swarm" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      master_host = string
      master_port = number
    }
  ))
  default = []
}

variable "integration_gke" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_update        = bool
      autoscale_cooldown = number
      autoscale_down = list(object(
        {
          evaluation_periods = number
        }
      ))
      autoscale_headroom = list(object(
        {
          cpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      autoscale_is_auto_config = bool
      autoscale_is_enabled     = bool
      autoscale_labels = set(object(
        {
          key   = string
          value = string
        }
      ))
      cluster_id = string
      location   = string
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
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_configs = set(object(
        {
          name = string
          type = string
        }
      ))
      alias_ip_ranges = set(object(
        {
          ip_cidr_range         = string
          subnetwork_range_name = string
        }
      ))
      network = string
    }
  ))
  default = []
}

variable "scaling_down_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type = string
      adjustment  = number
      cooldown    = number
      dimensions = list(object(
        {
          name  = string
          value = string
        }
      ))
      evaluation_periods = number
      metric_name        = string
      namespace          = string
      operator           = string
      period             = number
      policy_name        = string
      source             = string
      statistic          = string
      threshold          = number
      unit               = string
    }
  ))
  default = []
}

variable "scaling_up_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type = string
      adjustment  = number
      cooldown    = number
      dimensions = list(object(
        {
          name  = string
          value = string
        }
      ))
      evaluation_periods = number
      metric_name        = string
      namespace          = string
      operator           = string
      period             = number
      policy_name        = string
      source             = string
      statistic          = string
      threshold          = number
      unit               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_elastigroup_gke" "this" {
  cluster_id                 = var.cluster_id
  cluster_zone_name          = var.cluster_zone_name
  desired_capacity           = var.desired_capacity
  draining_timeout           = var.draining_timeout
  fallback_to_ondemand       = var.fallback_to_ondemand
  instance_types_ondemand    = var.instance_types_ondemand
  instance_types_preemptible = var.instance_types_preemptible
  ip_forwarding              = var.ip_forwarding
  max_size                   = var.max_size
  min_size                   = var.min_size
  name                       = var.name
  node_image                 = var.node_image
  ondemand_count             = var.ondemand_count
  preemptible_percentage     = var.preemptible_percentage
  service_account            = var.service_account
  shutdown_script            = var.shutdown_script
  startup_script             = var.startup_script
  tags                       = var.tags

  dynamic "backend_services" {
    for_each = var.backend_services
    content {
      location_type = backend_services.value["location_type"]
      scheme        = backend_services.value["scheme"]
      service_name  = backend_services.value["service_name"]

      dynamic "named_ports" {
        for_each = backend_services.value.named_ports
        content {
          name  = named_ports.value["name"]
          ports = named_ports.value["ports"]
        }
      }

    }
  }

  dynamic "disk" {
    for_each = var.disk
    content {
      auto_delete = disk.value["auto_delete"]
      boot        = disk.value["boot"]
      device_name = disk.value["device_name"]
      interface   = disk.value["interface"]
      mode        = disk.value["mode"]
      source      = disk.value["source"]
      type        = disk.value["type"]

      dynamic "initialize_params" {
        for_each = disk.value.initialize_params
        content {
          disk_size_gb = initialize_params.value["disk_size_gb"]
          disk_type    = initialize_params.value["disk_type"]
          source_image = initialize_params.value["source_image"]
        }
      }

    }
  }

  dynamic "gpu" {
    for_each = var.gpu
    content {
      count = gpu.value["count"]
      type  = gpu.value["type"]
    }
  }

  dynamic "instance_types_custom" {
    for_each = var.instance_types_custom
    content {
      memory_gib = instance_types_custom.value["memory_gib"]
      vcpu       = instance_types_custom.value["vcpu"]
    }
  }

  dynamic "integration_docker_swarm" {
    for_each = var.integration_docker_swarm
    content {
      master_host = integration_docker_swarm.value["master_host"]
      master_port = integration_docker_swarm.value["master_port"]
    }
  }

  dynamic "integration_gke" {
    for_each = var.integration_gke
    content {
      auto_update              = integration_gke.value["auto_update"]
      autoscale_cooldown       = integration_gke.value["autoscale_cooldown"]
      autoscale_is_auto_config = integration_gke.value["autoscale_is_auto_config"]
      autoscale_is_enabled     = integration_gke.value["autoscale_is_enabled"]
      cluster_id               = integration_gke.value["cluster_id"]
      location                 = integration_gke.value["location"]

      dynamic "autoscale_down" {
        for_each = integration_gke.value.autoscale_down
        content {
          evaluation_periods = autoscale_down.value["evaluation_periods"]
        }
      }

      dynamic "autoscale_headroom" {
        for_each = integration_gke.value.autoscale_headroom
        content {
          cpu_per_unit    = autoscale_headroom.value["cpu_per_unit"]
          memory_per_unit = autoscale_headroom.value["memory_per_unit"]
          num_of_units    = autoscale_headroom.value["num_of_units"]
        }
      }

      dynamic "autoscale_labels" {
        for_each = integration_gke.value.autoscale_labels
        content {
          key   = autoscale_labels.value["key"]
          value = autoscale_labels.value["value"]
        }
      }

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

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      network = network_interface.value["network"]

      dynamic "access_configs" {
        for_each = network_interface.value.access_configs
        content {
          name = access_configs.value["name"]
          type = access_configs.value["type"]
        }
      }

      dynamic "alias_ip_ranges" {
        for_each = network_interface.value.alias_ip_ranges
        content {
          ip_cidr_range         = alias_ip_ranges.value["ip_cidr_range"]
          subnetwork_range_name = alias_ip_ranges.value["subnetwork_range_name"]
        }
      }

    }
  }

  dynamic "scaling_down_policy" {
    for_each = var.scaling_down_policy
    content {
      action_type        = scaling_down_policy.value["action_type"]
      adjustment         = scaling_down_policy.value["adjustment"]
      cooldown           = scaling_down_policy.value["cooldown"]
      evaluation_periods = scaling_down_policy.value["evaluation_periods"]
      metric_name        = scaling_down_policy.value["metric_name"]
      namespace          = scaling_down_policy.value["namespace"]
      operator           = scaling_down_policy.value["operator"]
      period             = scaling_down_policy.value["period"]
      policy_name        = scaling_down_policy.value["policy_name"]
      source             = scaling_down_policy.value["source"]
      statistic          = scaling_down_policy.value["statistic"]
      threshold          = scaling_down_policy.value["threshold"]
      unit               = scaling_down_policy.value["unit"]

      dynamic "dimensions" {
        for_each = scaling_down_policy.value.dimensions
        content {
          name  = dimensions.value["name"]
          value = dimensions.value["value"]
        }
      }

    }
  }

  dynamic "scaling_up_policy" {
    for_each = var.scaling_up_policy
    content {
      action_type        = scaling_up_policy.value["action_type"]
      adjustment         = scaling_up_policy.value["adjustment"]
      cooldown           = scaling_up_policy.value["cooldown"]
      evaluation_periods = scaling_up_policy.value["evaluation_periods"]
      metric_name        = scaling_up_policy.value["metric_name"]
      namespace          = scaling_up_policy.value["namespace"]
      operator           = scaling_up_policy.value["operator"]
      period             = scaling_up_policy.value["period"]
      policy_name        = scaling_up_policy.value["policy_name"]
      source             = scaling_up_policy.value["source"]
      statistic          = scaling_up_policy.value["statistic"]
      threshold          = scaling_up_policy.value["threshold"]
      unit               = scaling_up_policy.value["unit"]

      dynamic "dimensions" {
        for_each = scaling_up_policy.value.dimensions
        content {
          name  = dimensions.value["name"]
          value = dimensions.value["value"]
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
  value       = spotinst_elastigroup_gke.this.id
}

output "max_size" {
  description = "returns a number"
  value       = spotinst_elastigroup_gke.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = spotinst_elastigroup_gke.this.min_size
}

output "this" {
  value = spotinst_elastigroup_gke.this
}
```

[top](#index)