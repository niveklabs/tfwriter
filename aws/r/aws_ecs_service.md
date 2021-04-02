# aws_ecs_service

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ecs_service" {
  source = "./modules/aws/r/aws_ecs_service"

  # cluster - (optional) is a type of string
  cluster = null
  # deployment_maximum_percent - (optional) is a type of number
  deployment_maximum_percent = null
  # deployment_minimum_healthy_percent - (optional) is a type of number
  deployment_minimum_healthy_percent = null
  # desired_count - (optional) is a type of number
  desired_count = null
  # enable_ecs_managed_tags - (optional) is a type of bool
  enable_ecs_managed_tags = null
  # enable_execute_command - (optional) is a type of bool
  enable_execute_command = null
  # force_new_deployment - (optional) is a type of bool
  force_new_deployment = null
  # health_check_grace_period_seconds - (optional) is a type of number
  health_check_grace_period_seconds = null
  # iam_role - (optional) is a type of string
  iam_role = null
  # launch_type - (optional) is a type of string
  launch_type = null
  # name - (required) is a type of string
  name = null
  # platform_version - (optional) is a type of string
  platform_version = null
  # propagate_tags - (optional) is a type of string
  propagate_tags = null
  # scheduling_strategy - (optional) is a type of string
  scheduling_strategy = null
  # tags - (optional) is a type of map of string
  tags = {}
  # task_definition - (optional) is a type of string
  task_definition = null
  # wait_for_steady_state - (optional) is a type of bool
  wait_for_steady_state = null

  capacity_provider_strategy = [{
    base              = null
    capacity_provider = null
    weight            = null
  }]

  deployment_circuit_breaker = [{
    enable   = null
    rollback = null
  }]

  deployment_controller = [{
    type = null
  }]

  load_balancer = [{
    container_name   = null
    container_port   = null
    elb_name         = null
    target_group_arn = null
  }]

  network_configuration = [{
    assign_public_ip = null
    security_groups  = []
    subnets          = []
  }]

  ordered_placement_strategy = [{
    field = null
    type  = null
  }]

  placement_constraints = [{
    expression = null
    type       = null
  }]

  service_registries = [{
    container_name = null
    container_port = null
    port           = null
    registry_arn   = null
  }]

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_maximum_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "deployment_minimum_healthy_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "desired_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_ecs_managed_tags" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_execute_command" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_new_deployment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "health_check_grace_period_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iam_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "propagate_tags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduling_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "task_definition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_for_steady_state" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "capacity_provider_strategy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      base              = number
      capacity_provider = string
      weight            = number
    }
  ))
  default = []
}

variable "deployment_circuit_breaker" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable   = bool
      rollback = bool
    }
  ))
  default = []
}

variable "deployment_controller" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "load_balancer" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      container_name   = string
      container_port   = number
      elb_name         = string
      target_group_arn = string
    }
  ))
  default = []
}

variable "network_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      assign_public_ip = bool
      security_groups  = set(string)
      subnets          = set(string)
    }
  ))
  default = []
}

variable "ordered_placement_strategy" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      field = string
      type  = string
    }
  ))
  default = []
}

variable "placement_constraints" {
  description = "nested block: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      expression = string
      type       = string
    }
  ))
  default = []
}

variable "service_registries" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      container_name = string
      container_port = number
      port           = number
      registry_arn   = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ecs_service" "this" {
  cluster                            = var.cluster
  deployment_maximum_percent         = var.deployment_maximum_percent
  deployment_minimum_healthy_percent = var.deployment_minimum_healthy_percent
  desired_count                      = var.desired_count
  enable_ecs_managed_tags            = var.enable_ecs_managed_tags
  enable_execute_command             = var.enable_execute_command
  force_new_deployment               = var.force_new_deployment
  health_check_grace_period_seconds  = var.health_check_grace_period_seconds
  iam_role                           = var.iam_role
  launch_type                        = var.launch_type
  name                               = var.name
  platform_version                   = var.platform_version
  propagate_tags                     = var.propagate_tags
  scheduling_strategy                = var.scheduling_strategy
  tags                               = var.tags
  task_definition                    = var.task_definition
  wait_for_steady_state              = var.wait_for_steady_state

  dynamic "capacity_provider_strategy" {
    for_each = var.capacity_provider_strategy
    content {
      base              = capacity_provider_strategy.value["base"]
      capacity_provider = capacity_provider_strategy.value["capacity_provider"]
      weight            = capacity_provider_strategy.value["weight"]
    }
  }

  dynamic "deployment_circuit_breaker" {
    for_each = var.deployment_circuit_breaker
    content {
      enable   = deployment_circuit_breaker.value["enable"]
      rollback = deployment_circuit_breaker.value["rollback"]
    }
  }

  dynamic "deployment_controller" {
    for_each = var.deployment_controller
    content {
      type = deployment_controller.value["type"]
    }
  }

  dynamic "load_balancer" {
    for_each = var.load_balancer
    content {
      container_name   = load_balancer.value["container_name"]
      container_port   = load_balancer.value["container_port"]
      elb_name         = load_balancer.value["elb_name"]
      target_group_arn = load_balancer.value["target_group_arn"]
    }
  }

  dynamic "network_configuration" {
    for_each = var.network_configuration
    content {
      assign_public_ip = network_configuration.value["assign_public_ip"]
      security_groups  = network_configuration.value["security_groups"]
      subnets          = network_configuration.value["subnets"]
    }
  }

  dynamic "ordered_placement_strategy" {
    for_each = var.ordered_placement_strategy
    content {
      field = ordered_placement_strategy.value["field"]
      type  = ordered_placement_strategy.value["type"]
    }
  }

  dynamic "placement_constraints" {
    for_each = var.placement_constraints
    content {
      expression = placement_constraints.value["expression"]
      type       = placement_constraints.value["type"]
    }
  }

  dynamic "service_registries" {
    for_each = var.service_registries
    content {
      container_name = service_registries.value["container_name"]
      container_port = service_registries.value["container_port"]
      port           = service_registries.value["port"]
      registry_arn   = service_registries.value["registry_arn"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster" {
  description = "returns a string"
  value       = aws_ecs_service.this.cluster
}

output "iam_role" {
  description = "returns a string"
  value       = aws_ecs_service.this.iam_role
}

output "id" {
  description = "returns a string"
  value       = aws_ecs_service.this.id
}

output "launch_type" {
  description = "returns a string"
  value       = aws_ecs_service.this.launch_type
}

output "platform_version" {
  description = "returns a string"
  value       = aws_ecs_service.this.platform_version
}

output "this" {
  value = aws_ecs_service.this
}
```

[top](#index)