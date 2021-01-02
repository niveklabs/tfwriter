# aws_batch_compute_environment

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_batch_compute_environment" {
  source = "./modules/aws/r/aws_batch_compute_environment"

  # compute_environment_name - (optional) is a type of string
  compute_environment_name = null
  # compute_environment_name_prefix - (optional) is a type of string
  compute_environment_name_prefix = null
  # service_role - (required) is a type of string
  service_role = null
  # state - (optional) is a type of string
  state = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null

  compute_resources = [{
    allocation_strategy = null
    bid_percentage      = null
    desired_vcpus       = null
    ec2_key_pair        = null
    image_id            = null
    instance_role       = null
    instance_type       = []
    launch_template = [{
      launch_template_id   = null
      launch_template_name = null
      version              = null
    }]
    max_vcpus           = null
    min_vcpus           = null
    security_group_ids  = []
    spot_iam_fleet_role = null
    subnets             = []
    tags                = {}
    type                = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compute_environment_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compute_environment_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_role" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "compute_resources" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allocation_strategy = string
      bid_percentage      = number
      desired_vcpus       = number
      ec2_key_pair        = string
      image_id            = string
      instance_role       = string
      instance_type       = set(string)
      launch_template = list(object(
        {
          launch_template_id   = string
          launch_template_name = string
          version              = string
        }
      ))
      max_vcpus           = number
      min_vcpus           = number
      security_group_ids  = set(string)
      spot_iam_fleet_role = string
      subnets             = set(string)
      tags                = map(string)
      type                = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_batch_compute_environment" "this" {
  compute_environment_name        = var.compute_environment_name
  compute_environment_name_prefix = var.compute_environment_name_prefix
  service_role                    = var.service_role
  state                           = var.state
  tags                            = var.tags
  type                            = var.type

  dynamic "compute_resources" {
    for_each = var.compute_resources
    content {
      allocation_strategy = compute_resources.value["allocation_strategy"]
      bid_percentage      = compute_resources.value["bid_percentage"]
      desired_vcpus       = compute_resources.value["desired_vcpus"]
      ec2_key_pair        = compute_resources.value["ec2_key_pair"]
      image_id            = compute_resources.value["image_id"]
      instance_role       = compute_resources.value["instance_role"]
      instance_type       = compute_resources.value["instance_type"]
      max_vcpus           = compute_resources.value["max_vcpus"]
      min_vcpus           = compute_resources.value["min_vcpus"]
      security_group_ids  = compute_resources.value["security_group_ids"]
      spot_iam_fleet_role = compute_resources.value["spot_iam_fleet_role"]
      subnets             = compute_resources.value["subnets"]
      tags                = compute_resources.value["tags"]
      type                = compute_resources.value["type"]

      dynamic "launch_template" {
        for_each = compute_resources.value.launch_template
        content {
          launch_template_id   = launch_template.value["launch_template_id"]
          launch_template_name = launch_template.value["launch_template_name"]
          version              = launch_template.value["version"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_batch_compute_environment.this.arn
}

output "compute_environment_name" {
  description = "returns a string"
  value       = aws_batch_compute_environment.this.compute_environment_name
}

output "ecs_cluster_arn" {
  description = "returns a string"
  value       = aws_batch_compute_environment.this.ecs_cluster_arn
}

output "id" {
  description = "returns a string"
  value       = aws_batch_compute_environment.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_batch_compute_environment.this.status
}

output "status_reason" {
  description = "returns a string"
  value       = aws_batch_compute_environment.this.status_reason
}

output "this" {
  value = aws_batch_compute_environment.this
}
```

[top](#index)