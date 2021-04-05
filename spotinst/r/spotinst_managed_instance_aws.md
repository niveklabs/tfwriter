# spotinst_managed_instance_aws

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
module "spotinst_managed_instance_aws" {
  source = "./modules/spotinst/r/spotinst_managed_instance_aws"

  # auto_healing - (optional) is a type of bool
  auto_healing = null
  # block_devices_mode - (optional) is a type of string
  block_devices_mode = null
  # cpu_credits - (optional) is a type of string
  cpu_credits = null
  # description - (optional) is a type of string
  description = null
  # draining_timeout - (optional) is a type of number
  draining_timeout = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # elastic_ip - (optional) is a type of string
  elastic_ip = null
  # enable_monitoring - (optional) is a type of bool
  enable_monitoring = null
  # fall_back_to_od - (optional) is a type of bool
  fall_back_to_od = null
  # grace_period - (optional) is a type of number
  grace_period = null
  # health_check_type - (optional) is a type of string
  health_check_type = null
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # image_id - (required) is a type of string
  image_id = null
  # instance_types - (required) is a type of list of string
  instance_types = []
  # key_pair - (optional) is a type of string
  key_pair = null
  # life_cycle - (optional) is a type of string
  life_cycle = null
  # name - (required) is a type of string
  name = null
  # optimization_windows - (optional) is a type of list of string
  optimization_windows = []
  # orientation - (optional) is a type of string
  orientation = null
  # persist_block_devices - (required) is a type of bool
  persist_block_devices = null
  # persist_private_ip - (optional) is a type of bool
  persist_private_ip = null
  # persist_root_device - (optional) is a type of bool
  persist_root_device = null
  # placement_tenancy - (optional) is a type of string
  placement_tenancy = null
  # preferred_type - (optional) is a type of string
  preferred_type = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # product - (required) is a type of string
  product = null
  # region - (optional) is a type of string
  region = null
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = []
  # shutdown_script - (optional) is a type of string
  shutdown_script = null
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []
  # unhealthy_duration - (optional) is a type of number
  unhealthy_duration = null
  # user_data - (optional) is a type of string
  user_data = null
  # utilize_reserved_instances - (optional) is a type of bool
  utilize_reserved_instances = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  integration_route53 = [{
    domains = [{
      hosted_zone_id  = null
      record_set_type = null
      record_sets = [{
        name           = null
        use_public_dns = null
        use_public_ip  = null
      }]
      spotinst_acct_id = null
    }]
  }]

  load_balancers = [{
    arn           = null
    auto_weight   = null
    az_awareness  = null
    balancer_id   = null
    name          = null
    target_set_id = null
    type          = null
  }]

  network_interface = [{
    associate_ipv6_address      = null
    associate_public_ip_address = null
    device_index                = null
  }]

  revert_to_spot = [{
    perform_at = null
  }]

  scheduled_task = [{
    cron_expression = null
    frequency       = null
    is_enabled      = null
    start_time      = null
    task_type       = null
  }]

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_healing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "block_devices_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_credits" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "draining_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "elastic_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fall_back_to_od" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_instance_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(required)"
  type        = string
}

variable "instance_types" {
  description = "(required)"
  type        = list(string)
}

variable "key_pair" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "life_cycle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "optimization_windows" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "orientation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "persist_block_devices" {
  description = "(required)"
  type        = bool
}

variable "persist_private_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "persist_root_device" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "placement_tenancy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "shutdown_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = list(string)
}

variable "unhealthy_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "utilize_reserved_instances" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "integration_route53" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      domains = set(object(
        {
          hosted_zone_id  = string
          record_set_type = string
          record_sets = set(object(
            {
              name           = string
              use_public_dns = bool
              use_public_ip  = bool
            }
          ))
          spotinst_acct_id = string
        }
      ))
    }
  ))
  default = []
}

variable "load_balancers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      arn           = string
      auto_weight   = bool
      az_awareness  = bool
      balancer_id   = string
      name          = string
      target_set_id = string
      type          = string
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      associate_ipv6_address      = bool
      associate_public_ip_address = bool
      device_index                = string
    }
  ))
  default = []
}

variable "revert_to_spot" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      perform_at = string
    }
  ))
  default = []
}

variable "scheduled_task" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cron_expression = string
      frequency       = string
      is_enabled      = bool
      start_time      = string
      task_type       = string
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_managed_instance_aws" "this" {
  auto_healing               = var.auto_healing
  block_devices_mode         = var.block_devices_mode
  cpu_credits                = var.cpu_credits
  description                = var.description
  draining_timeout           = var.draining_timeout
  ebs_optimized              = var.ebs_optimized
  elastic_ip                 = var.elastic_ip
  enable_monitoring          = var.enable_monitoring
  fall_back_to_od            = var.fall_back_to_od
  grace_period               = var.grace_period
  health_check_type          = var.health_check_type
  iam_instance_profile       = var.iam_instance_profile
  image_id                   = var.image_id
  instance_types             = var.instance_types
  key_pair                   = var.key_pair
  life_cycle                 = var.life_cycle
  name                       = var.name
  optimization_windows       = var.optimization_windows
  orientation                = var.orientation
  persist_block_devices      = var.persist_block_devices
  persist_private_ip         = var.persist_private_ip
  persist_root_device        = var.persist_root_device
  placement_tenancy          = var.placement_tenancy
  preferred_type             = var.preferred_type
  private_ip                 = var.private_ip
  product                    = var.product
  region                     = var.region
  security_group_ids         = var.security_group_ids
  shutdown_script            = var.shutdown_script
  subnet_ids                 = var.subnet_ids
  unhealthy_duration         = var.unhealthy_duration
  user_data                  = var.user_data
  utilize_reserved_instances = var.utilize_reserved_instances
  vpc_id                     = var.vpc_id

  dynamic "integration_route53" {
    for_each = var.integration_route53
    content {

      dynamic "domains" {
        for_each = integration_route53.value.domains
        content {
          hosted_zone_id   = domains.value["hosted_zone_id"]
          record_set_type  = domains.value["record_set_type"]
          spotinst_acct_id = domains.value["spotinst_acct_id"]

          dynamic "record_sets" {
            for_each = domains.value.record_sets
            content {
              name           = record_sets.value["name"]
              use_public_dns = record_sets.value["use_public_dns"]
              use_public_ip  = record_sets.value["use_public_ip"]
            }
          }

        }
      }

    }
  }

  dynamic "load_balancers" {
    for_each = var.load_balancers
    content {
      arn           = load_balancers.value["arn"]
      auto_weight   = load_balancers.value["auto_weight"]
      az_awareness  = load_balancers.value["az_awareness"]
      balancer_id   = load_balancers.value["balancer_id"]
      name          = load_balancers.value["name"]
      target_set_id = load_balancers.value["target_set_id"]
      type          = load_balancers.value["type"]
    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      associate_ipv6_address      = network_interface.value["associate_ipv6_address"]
      associate_public_ip_address = network_interface.value["associate_public_ip_address"]
      device_index                = network_interface.value["device_index"]
    }
  }

  dynamic "revert_to_spot" {
    for_each = var.revert_to_spot
    content {
      perform_at = revert_to_spot.value["perform_at"]
    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {
      cron_expression = scheduled_task.value["cron_expression"]
      frequency       = scheduled_task.value["frequency"]
      is_enabled      = scheduled_task.value["is_enabled"]
      start_time      = scheduled_task.value["start_time"]
      task_type       = scheduled_task.value["task_type"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      key   = tags.value["key"]
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ebs_optimized" {
  description = "returns a bool"
  value       = spotinst_managed_instance_aws.this.ebs_optimized
}

output "id" {
  description = "returns a string"
  value       = spotinst_managed_instance_aws.this.id
}

output "this" {
  value = spotinst_managed_instance_aws.this
}
```

[top](#index)