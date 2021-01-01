# aws_codedeploy_deployment_config

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_codedeploy_deployment_config" {
  source = "./modules/aws/r/aws_codedeploy_deployment_config"

  # compute_platform - (optional) is a type of string
  compute_platform = null
  # deployment_config_name - (required) is a type of string
  deployment_config_name = null

  minimum_healthy_hosts = [{
    type  = null
    value = null
  }]

  traffic_routing_config = [{
    time_based_canary = [{
      interval   = null
      percentage = null
    }]
    time_based_linear = [{
      interval   = null
      percentage = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "compute_platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_config_name" {
  description = "(required)"
  type        = string
}

variable "minimum_healthy_hosts" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type  = string
      value = number
    }
  ))
  default = []
}

variable "traffic_routing_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      time_based_canary = list(object(
        {
          interval   = number
          percentage = number
        }
      ))
      time_based_linear = list(object(
        {
          interval   = number
          percentage = number
        }
      ))
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_codedeploy_deployment_config" "this" {
  compute_platform       = var.compute_platform
  deployment_config_name = var.deployment_config_name

  dynamic "minimum_healthy_hosts" {
    for_each = var.minimum_healthy_hosts
    content {
      type  = minimum_healthy_hosts.value["type"]
      value = minimum_healthy_hosts.value["value"]
    }
  }

  dynamic "traffic_routing_config" {
    for_each = var.traffic_routing_config
    content {
      type = traffic_routing_config.value["type"]

      dynamic "time_based_canary" {
        for_each = traffic_routing_config.value.time_based_canary
        content {
          interval   = time_based_canary.value["interval"]
          percentage = time_based_canary.value["percentage"]
        }
      }

      dynamic "time_based_linear" {
        for_each = traffic_routing_config.value.time_based_linear
        content {
          interval   = time_based_linear.value["interval"]
          percentage = time_based_linear.value["percentage"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "deployment_config_id" {
  description = "returns a string"
  value       = aws_codedeploy_deployment_config.this.deployment_config_id
}

output "id" {
  description = "returns a string"
  value       = aws_codedeploy_deployment_config.this.id
}

output "this" {
  value = aws_codedeploy_deployment_config.this
}
```

[top](#index)