# aws_spot_fleet_request

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
module "aws_spot_fleet_request" {
  source = "./modules/aws/r/aws_spot_fleet_request"

  # allocation_strategy - (optional) is a type of string
  allocation_strategy = null
  # excess_capacity_termination_policy - (optional) is a type of string
  excess_capacity_termination_policy = null
  # fleet_type - (optional) is a type of string
  fleet_type = null
  # iam_fleet_role - (required) is a type of string
  iam_fleet_role = null
  # instance_interruption_behaviour - (optional) is a type of string
  instance_interruption_behaviour = null
  # instance_pools_to_use_count - (optional) is a type of number
  instance_pools_to_use_count = null
  # load_balancers - (optional) is a type of set of string
  load_balancers = []
  # replace_unhealthy_instances - (optional) is a type of bool
  replace_unhealthy_instances = null
  # spot_price - (optional) is a type of string
  spot_price = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_capacity - (required) is a type of number
  target_capacity = null
  # target_group_arns - (optional) is a type of set of string
  target_group_arns = []
  # terminate_instances_with_expiration - (optional) is a type of bool
  terminate_instances_with_expiration = null
  # valid_from - (optional) is a type of string
  valid_from = null
  # valid_until - (optional) is a type of string
  valid_until = null
  # wait_for_fulfillment - (optional) is a type of bool
  wait_for_fulfillment = null

  launch_specification = [{
    ami                         = null
    associate_public_ip_address = null
    availability_zone           = null
    ebs_block_device = [{
      delete_on_termination = null
      device_name           = null
      encrypted             = null
      iops                  = null
      kms_key_id            = null
      snapshot_id           = null
      throughput            = null
      volume_size           = null
      volume_type           = null
    }]
    ebs_optimized = null
    ephemeral_block_device = [{
      device_name  = null
      virtual_name = null
    }]
    iam_instance_profile     = null
    iam_instance_profile_arn = null
    instance_type            = null
    key_name                 = null
    monitoring               = null
    placement_group          = null
    placement_tenancy        = null
    root_block_device = [{
      delete_on_termination = null
      encrypted             = null
      iops                  = null
      kms_key_id            = null
      throughput            = null
      volume_size           = null
      volume_type           = null
    }]
    spot_price             = null
    subnet_id              = null
    tags                   = {}
    user_data              = null
    vpc_security_group_ids = []
    weighted_capacity      = null
  }]

  launch_template_config = [{
    launch_template_specification = [{
      id      = null
      name    = null
      version = null
    }]
    overrides = [{
      availability_zone = null
      instance_type     = null
      priority          = null
      spot_price        = null
      subnet_id         = null
      weighted_capacity = null
    }]
  }]

  spot_maintenance_strategies = [{
    capacity_rebalance = [{
      replacement_strategy = null
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
variable "allocation_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "excess_capacity_termination_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fleet_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_fleet_role" {
  description = "(required)"
  type        = string
}

variable "instance_interruption_behaviour" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_pools_to_use_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "load_balancers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "replace_unhealthy_instances" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "spot_price" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_capacity" {
  description = "(required)"
  type        = number
}

variable "target_group_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "terminate_instances_with_expiration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "valid_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "valid_until" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_for_fulfillment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "launch_specification" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ami                         = string
      associate_public_ip_address = bool
      availability_zone           = string
      ebs_block_device = set(object(
        {
          delete_on_termination = bool
          device_name           = string
          encrypted             = bool
          iops                  = number
          kms_key_id            = string
          snapshot_id           = string
          throughput            = number
          volume_size           = number
          volume_type           = string
        }
      ))
      ebs_optimized = bool
      ephemeral_block_device = set(object(
        {
          device_name  = string
          virtual_name = string
        }
      ))
      iam_instance_profile     = string
      iam_instance_profile_arn = string
      instance_type            = string
      key_name                 = string
      monitoring               = bool
      placement_group          = string
      placement_tenancy        = string
      root_block_device = set(object(
        {
          delete_on_termination = bool
          encrypted             = bool
          iops                  = number
          kms_key_id            = string
          throughput            = number
          volume_size           = number
          volume_type           = string
        }
      ))
      spot_price             = string
      subnet_id              = string
      tags                   = map(string)
      user_data              = string
      vpc_security_group_ids = set(string)
      weighted_capacity      = string
    }
  ))
  default = []
}

variable "launch_template_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      launch_template_specification = list(object(
        {
          id      = string
          name    = string
          version = string
        }
      ))
      overrides = set(object(
        {
          availability_zone = string
          instance_type     = string
          priority          = number
          spot_price        = string
          subnet_id         = string
          weighted_capacity = number
        }
      ))
    }
  ))
  default = []
}

variable "spot_maintenance_strategies" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      capacity_rebalance = list(object(
        {
          replacement_strategy = string
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
resource "aws_spot_fleet_request" "this" {
  # allocation_strategy - (optional) is a type of string
  allocation_strategy = var.allocation_strategy
  # excess_capacity_termination_policy - (optional) is a type of string
  excess_capacity_termination_policy = var.excess_capacity_termination_policy
  # fleet_type - (optional) is a type of string
  fleet_type = var.fleet_type
  # iam_fleet_role - (required) is a type of string
  iam_fleet_role = var.iam_fleet_role
  # instance_interruption_behaviour - (optional) is a type of string
  instance_interruption_behaviour = var.instance_interruption_behaviour
  # instance_pools_to_use_count - (optional) is a type of number
  instance_pools_to_use_count = var.instance_pools_to_use_count
  # load_balancers - (optional) is a type of set of string
  load_balancers = var.load_balancers
  # replace_unhealthy_instances - (optional) is a type of bool
  replace_unhealthy_instances = var.replace_unhealthy_instances
  # spot_price - (optional) is a type of string
  spot_price = var.spot_price
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target_capacity - (required) is a type of number
  target_capacity = var.target_capacity
  # target_group_arns - (optional) is a type of set of string
  target_group_arns = var.target_group_arns
  # terminate_instances_with_expiration - (optional) is a type of bool
  terminate_instances_with_expiration = var.terminate_instances_with_expiration
  # valid_from - (optional) is a type of string
  valid_from = var.valid_from
  # valid_until - (optional) is a type of string
  valid_until = var.valid_until
  # wait_for_fulfillment - (optional) is a type of bool
  wait_for_fulfillment = var.wait_for_fulfillment

  dynamic "launch_specification" {
    for_each = var.launch_specification
    content {
      # ami - (required) is a type of string
      ami = launch_specification.value["ami"]
      # associate_public_ip_address - (optional) is a type of bool
      associate_public_ip_address = launch_specification.value["associate_public_ip_address"]
      # availability_zone - (optional) is a type of string
      availability_zone = launch_specification.value["availability_zone"]
      # ebs_optimized - (optional) is a type of bool
      ebs_optimized = launch_specification.value["ebs_optimized"]
      # iam_instance_profile - (optional) is a type of string
      iam_instance_profile = launch_specification.value["iam_instance_profile"]
      # iam_instance_profile_arn - (optional) is a type of string
      iam_instance_profile_arn = launch_specification.value["iam_instance_profile_arn"]
      # instance_type - (required) is a type of string
      instance_type = launch_specification.value["instance_type"]
      # key_name - (optional) is a type of string
      key_name = launch_specification.value["key_name"]
      # monitoring - (optional) is a type of bool
      monitoring = launch_specification.value["monitoring"]
      # placement_group - (optional) is a type of string
      placement_group = launch_specification.value["placement_group"]
      # placement_tenancy - (optional) is a type of string
      placement_tenancy = launch_specification.value["placement_tenancy"]
      # spot_price - (optional) is a type of string
      spot_price = launch_specification.value["spot_price"]
      # subnet_id - (optional) is a type of string
      subnet_id = launch_specification.value["subnet_id"]
      # tags - (optional) is a type of map of string
      tags = launch_specification.value["tags"]
      # user_data - (optional) is a type of string
      user_data = launch_specification.value["user_data"]
      # vpc_security_group_ids - (optional) is a type of set of string
      vpc_security_group_ids = launch_specification.value["vpc_security_group_ids"]
      # weighted_capacity - (optional) is a type of string
      weighted_capacity = launch_specification.value["weighted_capacity"]

      dynamic "ebs_block_device" {
        for_each = launch_specification.value.ebs_block_device
        content {
          # delete_on_termination - (optional) is a type of bool
          delete_on_termination = ebs_block_device.value["delete_on_termination"]
          # device_name - (required) is a type of string
          device_name = ebs_block_device.value["device_name"]
          # encrypted - (optional) is a type of bool
          encrypted = ebs_block_device.value["encrypted"]
          # iops - (optional) is a type of number
          iops = ebs_block_device.value["iops"]
          # kms_key_id - (optional) is a type of string
          kms_key_id = ebs_block_device.value["kms_key_id"]
          # snapshot_id - (optional) is a type of string
          snapshot_id = ebs_block_device.value["snapshot_id"]
          # throughput - (optional) is a type of number
          throughput = ebs_block_device.value["throughput"]
          # volume_size - (optional) is a type of number
          volume_size = ebs_block_device.value["volume_size"]
          # volume_type - (optional) is a type of string
          volume_type = ebs_block_device.value["volume_type"]
        }
      }

      dynamic "ephemeral_block_device" {
        for_each = launch_specification.value.ephemeral_block_device
        content {
          # device_name - (required) is a type of string
          device_name = ephemeral_block_device.value["device_name"]
          # virtual_name - (required) is a type of string
          virtual_name = ephemeral_block_device.value["virtual_name"]
        }
      }

      dynamic "root_block_device" {
        for_each = launch_specification.value.root_block_device
        content {
          # delete_on_termination - (optional) is a type of bool
          delete_on_termination = root_block_device.value["delete_on_termination"]
          # encrypted - (optional) is a type of bool
          encrypted = root_block_device.value["encrypted"]
          # iops - (optional) is a type of number
          iops = root_block_device.value["iops"]
          # kms_key_id - (optional) is a type of string
          kms_key_id = root_block_device.value["kms_key_id"]
          # throughput - (optional) is a type of number
          throughput = root_block_device.value["throughput"]
          # volume_size - (optional) is a type of number
          volume_size = root_block_device.value["volume_size"]
          # volume_type - (optional) is a type of string
          volume_type = root_block_device.value["volume_type"]
        }
      }

    }
  }

  dynamic "launch_template_config" {
    for_each = var.launch_template_config
    content {

      dynamic "launch_template_specification" {
        for_each = launch_template_config.value.launch_template_specification
        content {
          # id - (optional) is a type of string
          id = launch_template_specification.value["id"]
          # name - (optional) is a type of string
          name = launch_template_specification.value["name"]
          # version - (optional) is a type of string
          version = launch_template_specification.value["version"]
        }
      }

      dynamic "overrides" {
        for_each = launch_template_config.value.overrides
        content {
          # availability_zone - (optional) is a type of string
          availability_zone = overrides.value["availability_zone"]
          # instance_type - (optional) is a type of string
          instance_type = overrides.value["instance_type"]
          # priority - (optional) is a type of number
          priority = overrides.value["priority"]
          # spot_price - (optional) is a type of string
          spot_price = overrides.value["spot_price"]
          # subnet_id - (optional) is a type of string
          subnet_id = overrides.value["subnet_id"]
          # weighted_capacity - (optional) is a type of number
          weighted_capacity = overrides.value["weighted_capacity"]
        }
      }

    }
  }

  dynamic "spot_maintenance_strategies" {
    for_each = var.spot_maintenance_strategies
    content {

      dynamic "capacity_rebalance" {
        for_each = spot_maintenance_strategies.value.capacity_rebalance
        content {
          # replacement_strategy - (optional) is a type of string
          replacement_strategy = capacity_rebalance.value["replacement_strategy"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_token" {
  description = "returns a string"
  value       = aws_spot_fleet_request.this.client_token
}

output "id" {
  description = "returns a string"
  value       = aws_spot_fleet_request.this.id
}

output "load_balancers" {
  description = "returns a set of string"
  value       = aws_spot_fleet_request.this.load_balancers
}

output "spot_request_state" {
  description = "returns a string"
  value       = aws_spot_fleet_request.this.spot_request_state
}

output "target_group_arns" {
  description = "returns a set of string"
  value       = aws_spot_fleet_request.this.target_group_arns
}

output "this" {
  value = aws_spot_fleet_request.this
}
```

[top](#index)