# aws_ecs_task_definition

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_ecs_task_definition" {
  source = "./modules/aws/r/aws_ecs_task_definition"

  # container_definitions - (required) is a type of string
  container_definitions = null
  # cpu - (optional) is a type of string
  cpu = null
  # execution_role_arn - (optional) is a type of string
  execution_role_arn = null
  # family - (required) is a type of string
  family = null
  # ipc_mode - (optional) is a type of string
  ipc_mode = null
  # memory - (optional) is a type of string
  memory = null
  # network_mode - (optional) is a type of string
  network_mode = null
  # pid_mode - (optional) is a type of string
  pid_mode = null
  # requires_compatibilities - (optional) is a type of set of string
  requires_compatibilities = []
  # tags - (optional) is a type of map of string
  tags = {}
  # task_role_arn - (optional) is a type of string
  task_role_arn = null

  inference_accelerator = [{
    device_name = null
    device_type = null
  }]

  placement_constraints = [{
    expression = null
    type       = null
  }]

  proxy_configuration = [{
    container_name = null
    properties     = {}
    type           = null
  }]

  volume = [{
    docker_volume_configuration = [{
      autoprovision = null
      driver        = null
      driver_opts   = {}
      labels        = {}
      scope         = null
    }]
    efs_volume_configuration = [{
      authorization_config = [{
        access_point_id = null
        iam             = null
      }]
      file_system_id          = null
      root_directory          = null
      transit_encryption      = null
      transit_encryption_port = null
    }]
    host_path = null
    name      = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "container_definitions" {
  description = "(required)"
  type        = string
}

variable "cpu" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "execution_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "family" {
  description = "(required)"
  type        = string
}

variable "ipc_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pid_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "requires_compatibilities" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "task_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inference_accelerator" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      device_name = string
      device_type = string
    }
  ))
  default = []
}

variable "placement_constraints" {
  description = "nested mode: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      expression = string
      type       = string
    }
  ))
  default = []
}

variable "proxy_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      container_name = string
      properties     = map(string)
      type           = string
    }
  ))
  default = []
}

variable "volume" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      docker_volume_configuration = list(object(
        {
          autoprovision = bool
          driver        = string
          driver_opts   = map(string)
          labels        = map(string)
          scope         = string
        }
      ))
      efs_volume_configuration = list(object(
        {
          authorization_config = list(object(
            {
              access_point_id = string
              iam             = string
            }
          ))
          file_system_id          = string
          root_directory          = string
          transit_encryption      = string
          transit_encryption_port = number
        }
      ))
      host_path = string
      name      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_ecs_task_definition" "this" {
  container_definitions    = var.container_definitions
  cpu                      = var.cpu
  execution_role_arn       = var.execution_role_arn
  family                   = var.family
  ipc_mode                 = var.ipc_mode
  memory                   = var.memory
  network_mode             = var.network_mode
  pid_mode                 = var.pid_mode
  requires_compatibilities = var.requires_compatibilities
  tags                     = var.tags
  task_role_arn            = var.task_role_arn

  dynamic "inference_accelerator" {
    for_each = var.inference_accelerator
    content {
      device_name = inference_accelerator.value["device_name"]
      device_type = inference_accelerator.value["device_type"]
    }
  }

  dynamic "placement_constraints" {
    for_each = var.placement_constraints
    content {
      expression = placement_constraints.value["expression"]
      type       = placement_constraints.value["type"]
    }
  }

  dynamic "proxy_configuration" {
    for_each = var.proxy_configuration
    content {
      container_name = proxy_configuration.value["container_name"]
      properties     = proxy_configuration.value["properties"]
      type           = proxy_configuration.value["type"]
    }
  }

  dynamic "volume" {
    for_each = var.volume
    content {
      host_path = volume.value["host_path"]
      name      = volume.value["name"]

      dynamic "docker_volume_configuration" {
        for_each = volume.value.docker_volume_configuration
        content {
          autoprovision = docker_volume_configuration.value["autoprovision"]
          driver        = docker_volume_configuration.value["driver"]
          driver_opts   = docker_volume_configuration.value["driver_opts"]
          labels        = docker_volume_configuration.value["labels"]
          scope         = docker_volume_configuration.value["scope"]
        }
      }

      dynamic "efs_volume_configuration" {
        for_each = volume.value.efs_volume_configuration
        content {
          file_system_id          = efs_volume_configuration.value["file_system_id"]
          root_directory          = efs_volume_configuration.value["root_directory"]
          transit_encryption      = efs_volume_configuration.value["transit_encryption"]
          transit_encryption_port = efs_volume_configuration.value["transit_encryption_port"]

          dynamic "authorization_config" {
            for_each = efs_volume_configuration.value.authorization_config
            content {
              access_point_id = authorization_config.value["access_point_id"]
              iam             = authorization_config.value["iam"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ecs_task_definition.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ecs_task_definition.this.id
}

output "network_mode" {
  description = "returns a string"
  value       = aws_ecs_task_definition.this.network_mode
}

output "revision" {
  description = "returns a number"
  value       = aws_ecs_task_definition.this.revision
}

output "this" {
  value = aws_ecs_task_definition.this
}
```

[top](#index)