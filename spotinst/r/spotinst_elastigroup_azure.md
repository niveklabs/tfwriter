# spotinst_elastigroup_azure

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
module "spotinst_elastigroup_azure" {
  source = "./modules/spotinst/r/spotinst_elastigroup_azure"

  # custom_data - (optional) is a type of string
  custom_data = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # low_priority_sizes - (required) is a type of list of string
  low_priority_sizes = []
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # od_sizes - (required) is a type of list of string
  od_sizes = []
  # product - (required) is a type of string
  product = null
  # region - (required) is a type of string
  region = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # shutdown_script - (optional) is a type of string
  shutdown_script = null
  # user_data - (optional) is a type of string
  user_data = null

  health_check = [{
    auto_healing      = null
    grace_period      = null
    health_check_type = null
  }]

  image = [{
    custom = [{
      image_name          = null
      resource_group_name = null
    }]
    marketplace = [{
      offer     = null
      publisher = null
      sku       = null
    }]
  }]

  integration_kubernetes = [{
    cluster_identifier = null
  }]

  integration_multai_runtime = [{
    deployment_id = null
  }]

  load_balancers = [{
    auto_weight   = null
    balancer_id   = null
    target_set_id = null
    type          = null
  }]

  login = [{
    password       = null
    ssh_public_key = null
    user_name      = null
  }]

  managed_service_identities = [{
    name                = null
    resource_group_name = null
  }]

  network = [{
    additional_ip_configs = [{
      name               = null
      private_ip_version = null
    }]
    assign_public_ip     = null
    resource_group_name  = null
    subnet_name          = null
    virtual_network_name = null
  }]

  scaling_down_policy = [{
    action_type = null
    adjustment  = null
    cooldown    = null
    dimensions = [{
      name  = null
      value = null
    }]
    evaluation_periods  = null
    max_target_capacity = null
    maximum             = null
    metric_name         = null
    min_target_capacity = null
    minimum             = null
    namespace           = null
    operator            = null
    period              = null
    policy_name         = null
    statistic           = null
    target              = null
    threshold           = null
    unit                = null
  }]

  scaling_up_policy = [{
    action_type = null
    adjustment  = null
    cooldown    = null
    dimensions = [{
      name  = null
      value = null
    }]
    evaluation_periods  = null
    max_target_capacity = null
    maximum             = null
    metric_name         = null
    min_target_capacity = null
    minimum             = null
    namespace           = null
    operator            = null
    period              = null
    policy_name         = null
    statistic           = null
    target              = null
    threshold           = null
    unit                = null
  }]

  scheduled_task = [{
    adjustment            = null
    adjustment_percentage = null
    batch_size_percentage = null
    cron_expression       = null
    grace_period          = null
    is_enabled            = null
    scale_max_capacity    = null
    scale_min_capacity    = null
    scale_target_capacity = null
    task_type             = null
  }]

  strategy = [{
    draining_timeout        = null
    low_priority_percentage = null
    od_count                = null
  }]

  update_policy = [{
    roll_config = [{
      batch_size_percentage = null
      grace_period          = null
      health_check_type     = null
    }]
    should_roll = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "low_priority_sizes" {
  description = "(required)"
  type        = list(string)
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

variable "od_sizes" {
  description = "(required)"
  type        = list(string)
}

variable "product" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "shutdown_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_healing      = bool
      grace_period      = number
      health_check_type = string
    }
  ))
  default = []
}

variable "image" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      custom = list(object(
        {
          image_name          = string
          resource_group_name = string
        }
      ))
      marketplace = list(object(
        {
          offer     = string
          publisher = string
          sku       = string
        }
      ))
    }
  ))
  default = []
}

variable "integration_kubernetes" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cluster_identifier = string
    }
  ))
  default = []
}

variable "integration_multai_runtime" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      deployment_id = string
    }
  ))
  default = []
}

variable "load_balancers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auto_weight   = bool
      balancer_id   = string
      target_set_id = string
      type          = string
    }
  ))
  default = []
}

variable "login" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password       = string
      ssh_public_key = string
      user_name      = string
    }
  ))
  default = []
}

variable "managed_service_identities" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name                = string
      resource_group_name = string
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      additional_ip_configs = list(object(
        {
          name               = string
          private_ip_version = string
        }
      ))
      assign_public_ip     = bool
      resource_group_name  = string
      subnet_name          = string
      virtual_network_name = string
    }
  ))
}

variable "scaling_down_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type = string
      adjustment  = string
      cooldown    = number
      dimensions = list(object(
        {
          name  = string
          value = string
        }
      ))
      evaluation_periods  = number
      max_target_capacity = string
      maximum             = string
      metric_name         = string
      min_target_capacity = string
      minimum             = string
      namespace           = string
      operator            = string
      period              = number
      policy_name         = string
      statistic           = string
      target              = string
      threshold           = number
      unit                = string
    }
  ))
  default = []
}

variable "scaling_up_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type = string
      adjustment  = string
      cooldown    = number
      dimensions = list(object(
        {
          name  = string
          value = string
        }
      ))
      evaluation_periods  = number
      max_target_capacity = string
      maximum             = string
      metric_name         = string
      min_target_capacity = string
      minimum             = string
      namespace           = string
      operator            = string
      period              = number
      policy_name         = string
      statistic           = string
      target              = string
      threshold           = number
      unit                = string
    }
  ))
  default = []
}

variable "scheduled_task" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      adjustment            = string
      adjustment_percentage = string
      batch_size_percentage = string
      cron_expression       = string
      grace_period          = string
      is_enabled            = bool
      scale_max_capacity    = string
      scale_min_capacity    = string
      scale_target_capacity = string
      task_type             = string
    }
  ))
  default = []
}

variable "strategy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      draining_timeout        = number
      low_priority_percentage = number
      od_count                = number
    }
  ))
}

variable "update_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      roll_config = list(object(
        {
          batch_size_percentage = number
          grace_period          = number
          health_check_type     = string
        }
      ))
      should_roll = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_elastigroup_azure" "this" {
  custom_data         = var.custom_data
  desired_capacity    = var.desired_capacity
  low_priority_sizes  = var.low_priority_sizes
  max_size            = var.max_size
  min_size            = var.min_size
  name                = var.name
  od_sizes            = var.od_sizes
  product             = var.product
  region              = var.region
  resource_group_name = var.resource_group_name
  shutdown_script     = var.shutdown_script
  user_data           = var.user_data

  dynamic "health_check" {
    for_each = var.health_check
    content {
      auto_healing      = health_check.value["auto_healing"]
      grace_period      = health_check.value["grace_period"]
      health_check_type = health_check.value["health_check_type"]
    }
  }

  dynamic "image" {
    for_each = var.image
    content {

      dynamic "custom" {
        for_each = image.value.custom
        content {
          image_name          = custom.value["image_name"]
          resource_group_name = custom.value["resource_group_name"]
        }
      }

      dynamic "marketplace" {
        for_each = image.value.marketplace
        content {
          offer     = marketplace.value["offer"]
          publisher = marketplace.value["publisher"]
          sku       = marketplace.value["sku"]
        }
      }

    }
  }

  dynamic "integration_kubernetes" {
    for_each = var.integration_kubernetes
    content {
      cluster_identifier = integration_kubernetes.value["cluster_identifier"]
    }
  }

  dynamic "integration_multai_runtime" {
    for_each = var.integration_multai_runtime
    content {
      deployment_id = integration_multai_runtime.value["deployment_id"]
    }
  }

  dynamic "load_balancers" {
    for_each = var.load_balancers
    content {
      auto_weight   = load_balancers.value["auto_weight"]
      balancer_id   = load_balancers.value["balancer_id"]
      target_set_id = load_balancers.value["target_set_id"]
      type          = load_balancers.value["type"]
    }
  }

  dynamic "login" {
    for_each = var.login
    content {
      password       = login.value["password"]
      ssh_public_key = login.value["ssh_public_key"]
      user_name      = login.value["user_name"]
    }
  }

  dynamic "managed_service_identities" {
    for_each = var.managed_service_identities
    content {
      name                = managed_service_identities.value["name"]
      resource_group_name = managed_service_identities.value["resource_group_name"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      assign_public_ip     = network.value["assign_public_ip"]
      resource_group_name  = network.value["resource_group_name"]
      subnet_name          = network.value["subnet_name"]
      virtual_network_name = network.value["virtual_network_name"]

      dynamic "additional_ip_configs" {
        for_each = network.value.additional_ip_configs
        content {
          name               = additional_ip_configs.value["name"]
          private_ip_version = additional_ip_configs.value["private_ip_version"]
        }
      }

    }
  }

  dynamic "scaling_down_policy" {
    for_each = var.scaling_down_policy
    content {
      action_type         = scaling_down_policy.value["action_type"]
      adjustment          = scaling_down_policy.value["adjustment"]
      cooldown            = scaling_down_policy.value["cooldown"]
      evaluation_periods  = scaling_down_policy.value["evaluation_periods"]
      max_target_capacity = scaling_down_policy.value["max_target_capacity"]
      maximum             = scaling_down_policy.value["maximum"]
      metric_name         = scaling_down_policy.value["metric_name"]
      min_target_capacity = scaling_down_policy.value["min_target_capacity"]
      minimum             = scaling_down_policy.value["minimum"]
      namespace           = scaling_down_policy.value["namespace"]
      operator            = scaling_down_policy.value["operator"]
      period              = scaling_down_policy.value["period"]
      policy_name         = scaling_down_policy.value["policy_name"]
      statistic           = scaling_down_policy.value["statistic"]
      target              = scaling_down_policy.value["target"]
      threshold           = scaling_down_policy.value["threshold"]
      unit                = scaling_down_policy.value["unit"]

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
      action_type         = scaling_up_policy.value["action_type"]
      adjustment          = scaling_up_policy.value["adjustment"]
      cooldown            = scaling_up_policy.value["cooldown"]
      evaluation_periods  = scaling_up_policy.value["evaluation_periods"]
      max_target_capacity = scaling_up_policy.value["max_target_capacity"]
      maximum             = scaling_up_policy.value["maximum"]
      metric_name         = scaling_up_policy.value["metric_name"]
      min_target_capacity = scaling_up_policy.value["min_target_capacity"]
      minimum             = scaling_up_policy.value["minimum"]
      namespace           = scaling_up_policy.value["namespace"]
      operator            = scaling_up_policy.value["operator"]
      period              = scaling_up_policy.value["period"]
      policy_name         = scaling_up_policy.value["policy_name"]
      statistic           = scaling_up_policy.value["statistic"]
      target              = scaling_up_policy.value["target"]
      threshold           = scaling_up_policy.value["threshold"]
      unit                = scaling_up_policy.value["unit"]

      dynamic "dimensions" {
        for_each = scaling_up_policy.value.dimensions
        content {
          name  = dimensions.value["name"]
          value = dimensions.value["value"]
        }
      }

    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {
      adjustment            = scheduled_task.value["adjustment"]
      adjustment_percentage = scheduled_task.value["adjustment_percentage"]
      batch_size_percentage = scheduled_task.value["batch_size_percentage"]
      cron_expression       = scheduled_task.value["cron_expression"]
      grace_period          = scheduled_task.value["grace_period"]
      is_enabled            = scheduled_task.value["is_enabled"]
      scale_max_capacity    = scheduled_task.value["scale_max_capacity"]
      scale_min_capacity    = scheduled_task.value["scale_min_capacity"]
      scale_target_capacity = scheduled_task.value["scale_target_capacity"]
      task_type             = scheduled_task.value["task_type"]
    }
  }

  dynamic "strategy" {
    for_each = var.strategy
    content {
      draining_timeout        = strategy.value["draining_timeout"]
      low_priority_percentage = strategy.value["low_priority_percentage"]
      od_count                = strategy.value["od_count"]
    }
  }

  dynamic "update_policy" {
    for_each = var.update_policy
    content {
      should_roll = update_policy.value["should_roll"]

      dynamic "roll_config" {
        for_each = update_policy.value.roll_config
        content {
          batch_size_percentage = roll_config.value["batch_size_percentage"]
          grace_period          = roll_config.value["grace_period"]
          health_check_type     = roll_config.value["health_check_type"]
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
  value       = spotinst_elastigroup_azure.this.id
}

output "max_size" {
  description = "returns a number"
  value       = spotinst_elastigroup_azure.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = spotinst_elastigroup_azure.this.min_size
}

output "this" {
  value = spotinst_elastigroup_azure.this
}
```

[top](#index)