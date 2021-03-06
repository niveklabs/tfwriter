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
    aws = ">= 3.35.0"
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
  description = "nested block: NestingList, min items: 0, max items: 1"
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
  # compute_environment_name - (optional) is a type of string
  compute_environment_name = var.compute_environment_name
  # compute_environment_name_prefix - (optional) is a type of string
  compute_environment_name_prefix = var.compute_environment_name_prefix
  # service_role - (required) is a type of string
  service_role = var.service_role
  # state - (optional) is a type of string
  state = var.state
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type

  dynamic "compute_resources" {
    for_each = var.compute_resources
    content {
      # allocation_strategy - (optional) is a type of string
      allocation_strategy = compute_resources.value["allocation_strategy"]
      # bid_percentage - (optional) is a type of number
      bid_percentage = compute_resources.value["bid_percentage"]
      # desired_vcpus - (optional) is a type of number
      desired_vcpus = compute_resources.value["desired_vcpus"]
      # ec2_key_pair - (optional) is a type of string
      ec2_key_pair = compute_resources.value["ec2_key_pair"]
      # image_id - (optional) is a type of string
      image_id = compute_resources.value["image_id"]
      # instance_role - (required) is a type of string
      instance_role = compute_resources.value["instance_role"]
      # instance_type - (required) is a type of set of string
      instance_type = compute_resources.value["instance_type"]
      # max_vcpus - (required) is a type of number
      max_vcpus = compute_resources.value["max_vcpus"]
      # min_vcpus - (required) is a type of number
      min_vcpus = compute_resources.value["min_vcpus"]
      # security_group_ids - (required) is a type of set of string
      security_group_ids = compute_resources.value["security_group_ids"]
      # spot_iam_fleet_role - (optional) is a type of string
      spot_iam_fleet_role = compute_resources.value["spot_iam_fleet_role"]
      # subnets - (required) is a type of set of string
      subnets = compute_resources.value["subnets"]
      # tags - (optional) is a type of map of string
      tags = compute_resources.value["tags"]
      # type - (required) is a type of string
      type = compute_resources.value["type"]

      dynamic "launch_template" {
        for_each = compute_resources.value.launch_template
        content {
          # launch_template_id - (optional) is a type of string
          launch_template_id = launch_template.value["launch_template_id"]
          # launch_template_name - (optional) is a type of string
          launch_template_name = launch_template.value["launch_template_name"]
          # version - (optional) is a type of string
          version = launch_template.value["version"]
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