# aws_gamelift_fleet

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_gamelift_fleet" {
  source = "./modules/aws/r/aws_gamelift_fleet"

  # build_id - (required) is a type of string
  build_id = null
  # description - (optional) is a type of string
  description = null
  # ec2_instance_type - (required) is a type of string
  ec2_instance_type = null
  # fleet_type - (optional) is a type of string
  fleet_type = null
  # instance_role_arn - (optional) is a type of string
  instance_role_arn = null
  # metric_groups - (optional) is a type of list of string
  metric_groups = []
  # name - (required) is a type of string
  name = null
  # new_game_session_protection_policy - (optional) is a type of string
  new_game_session_protection_policy = null
  # tags - (optional) is a type of map of string
  tags = {}

  ec2_inbound_permission = [{
    from_port = null
    ip_range  = null
    protocol  = null
    to_port   = null
  }]

  resource_creation_limit_policy = [{
    new_game_sessions_per_creator = null
    policy_period_in_minutes      = null
  }]

  runtime_configuration = [{
    game_session_activation_timeout_seconds = null
    max_concurrent_game_session_activations = null
    server_process = [{
      concurrent_executions = null
      launch_path           = null
      parameters            = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "build_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ec2_instance_type" {
  description = "(required)"
  type        = string
}

variable "fleet_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metric_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "new_game_session_protection_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ec2_inbound_permission" {
  description = "nested block: NestingList, min items: 0, max items: 50"
  type = set(object(
    {
      from_port = number
      ip_range  = string
      protocol  = string
      to_port   = number
    }
  ))
  default = []
}

variable "resource_creation_limit_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      new_game_sessions_per_creator = number
      policy_period_in_minutes      = number
    }
  ))
  default = []
}

variable "runtime_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      game_session_activation_timeout_seconds = number
      max_concurrent_game_session_activations = number
      server_process = list(object(
        {
          concurrent_executions = number
          launch_path           = string
          parameters            = string
        }
      ))
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_gamelift_fleet" "this" {
  build_id                           = var.build_id
  description                        = var.description
  ec2_instance_type                  = var.ec2_instance_type
  fleet_type                         = var.fleet_type
  instance_role_arn                  = var.instance_role_arn
  metric_groups                      = var.metric_groups
  name                               = var.name
  new_game_session_protection_policy = var.new_game_session_protection_policy
  tags                               = var.tags

  dynamic "ec2_inbound_permission" {
    for_each = var.ec2_inbound_permission
    content {
      from_port = ec2_inbound_permission.value["from_port"]
      ip_range  = ec2_inbound_permission.value["ip_range"]
      protocol  = ec2_inbound_permission.value["protocol"]
      to_port   = ec2_inbound_permission.value["to_port"]
    }
  }

  dynamic "resource_creation_limit_policy" {
    for_each = var.resource_creation_limit_policy
    content {
      new_game_sessions_per_creator = resource_creation_limit_policy.value["new_game_sessions_per_creator"]
      policy_period_in_minutes      = resource_creation_limit_policy.value["policy_period_in_minutes"]
    }
  }

  dynamic "runtime_configuration" {
    for_each = var.runtime_configuration
    content {
      game_session_activation_timeout_seconds = runtime_configuration.value["game_session_activation_timeout_seconds"]
      max_concurrent_game_session_activations = runtime_configuration.value["max_concurrent_game_session_activations"]

      dynamic "server_process" {
        for_each = runtime_configuration.value.server_process
        content {
          concurrent_executions = server_process.value["concurrent_executions"]
          launch_path           = server_process.value["launch_path"]
          parameters            = server_process.value["parameters"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_gamelift_fleet.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_gamelift_fleet.this.id
}

output "log_paths" {
  description = "returns a list of string"
  value       = aws_gamelift_fleet.this.log_paths
}

output "metric_groups" {
  description = "returns a list of string"
  value       = aws_gamelift_fleet.this.metric_groups
}

output "operating_system" {
  description = "returns a string"
  value       = aws_gamelift_fleet.this.operating_system
}

output "this" {
  value = aws_gamelift_fleet.this
}
```

[top](#index)