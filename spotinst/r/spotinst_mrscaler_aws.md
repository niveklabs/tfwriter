# spotinst_mrscaler_aws

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
module "spotinst_mrscaler_aws" {
  source = "./modules/spotinst/r/spotinst_mrscaler_aws"

  # additional_info - (optional) is a type of string
  additional_info = null
  # additional_primary_security_groups - (optional) is a type of list of string
  additional_primary_security_groups = []
  # additional_replica_security_groups - (optional) is a type of list of string
  additional_replica_security_groups = []
  # availability_zones - (optional) is a type of list of string
  availability_zones = []
  # cluster_id - (optional) is a type of string
  cluster_id = null
  # core_desired_capacity - (optional) is a type of number
  core_desired_capacity = null
  # core_ebs_optimized - (optional) is a type of bool
  core_ebs_optimized = null
  # core_instance_types - (optional) is a type of list of string
  core_instance_types = []
  # core_lifecycle - (optional) is a type of string
  core_lifecycle = null
  # core_max_size - (optional) is a type of number
  core_max_size = null
  # core_min_size - (optional) is a type of number
  core_min_size = null
  # core_unit - (optional) is a type of string
  core_unit = null
  # custom_ami_id - (optional) is a type of string
  custom_ami_id = null
  # description - (optional) is a type of string
  description = null
  # ebs_root_volume_size - (optional) is a type of number
  ebs_root_volume_size = null
  # ec2_key_name - (optional) is a type of string
  ec2_key_name = null
  # expose_cluster_id - (optional) is a type of bool
  expose_cluster_id = null
  # job_flow_role - (optional) is a type of string
  job_flow_role = null
  # keep_job_flow_alive - (optional) is a type of bool
  keep_job_flow_alive = null
  # log_uri - (optional) is a type of string
  log_uri = null
  # managed_primary_security_group - (optional) is a type of string
  managed_primary_security_group = null
  # managed_replica_security_group - (optional) is a type of string
  managed_replica_security_group = null
  # master_ebs_optimized - (optional) is a type of bool
  master_ebs_optimized = null
  # master_instance_types - (optional) is a type of list of string
  master_instance_types = []
  # master_lifecycle - (optional) is a type of string
  master_lifecycle = null
  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # release_label - (optional) is a type of string
  release_label = null
  # repo_upgrade_on_boot - (optional) is a type of string
  repo_upgrade_on_boot = null
  # retries - (optional) is a type of number
  retries = null
  # security_config - (optional) is a type of string
  security_config = null
  # service_access_security_group - (optional) is a type of string
  service_access_security_group = null
  # service_role - (optional) is a type of string
  service_role = null
  # strategy - (required) is a type of string
  strategy = null
  # task_desired_capacity - (optional) is a type of number
  task_desired_capacity = null
  # task_ebs_optimized - (optional) is a type of bool
  task_ebs_optimized = null
  # task_instance_types - (optional) is a type of list of string
  task_instance_types = []
  # task_lifecycle - (optional) is a type of string
  task_lifecycle = null
  # task_max_size - (optional) is a type of number
  task_max_size = null
  # task_min_size - (optional) is a type of number
  task_min_size = null
  # task_unit - (optional) is a type of string
  task_unit = null
  # termination_protected - (optional) is a type of bool
  termination_protected = null
  # visible_to_all_users - (optional) is a type of bool
  visible_to_all_users = null

  applications = [{
    args    = []
    name    = null
    version = null
  }]

  bootstrap_actions_file = [{
    bucket = null
    key    = null
  }]

  configurations_file = [{
    bucket = null
    key    = null
  }]

  core_ebs_block_device = [{
    iops                 = null
    size_in_gb           = null
    volume_type          = null
    volumes_per_instance = null
  }]

  core_scaling_down_policy = [{
    action_type         = null
    adjustment          = null
    cooldown            = null
    dimensions          = {}
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

  core_scaling_up_policy = [{
    action_type         = null
    adjustment          = null
    cooldown            = null
    dimensions          = {}
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

  instance_weights = [{
    instance_type     = null
    weighted_capacity = null
  }]

  master_ebs_block_device = [{
    iops                 = null
    size_in_gb           = null
    volume_type          = null
    volumes_per_instance = null
  }]

  provisioning_timeout = [{
    timeout        = null
    timeout_action = null
  }]

  scheduled_task = [{
    cron                = null
    desired_capacity    = null
    instance_group_type = null
    is_enabled          = null
    max_capacity        = null
    min_capacity        = null
    task_type           = null
  }]

  steps_file = [{
    bucket = null
    key    = null
  }]

  tags = [{
    key   = null
    value = null
  }]

  task_ebs_block_device = [{
    iops                 = null
    size_in_gb           = null
    volume_type          = null
    volumes_per_instance = null
  }]

  task_scaling_down_policy = [{
    action_type         = null
    adjustment          = null
    cooldown            = null
    dimensions          = {}
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

  task_scaling_up_policy = [{
    action_type         = null
    adjustment          = null
    cooldown            = null
    dimensions          = {}
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

  termination_policies = [{
    statements = [{
      evaluation_periods = null
      metric_name        = null
      namespace          = null
      operator           = null
      period             = null
      statistic          = null
      threshold          = null
      unit               = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "additional_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "additional_primary_security_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "additional_replica_security_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "availability_zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "core_desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "core_instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "core_lifecycle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "core_max_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_min_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_ami_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebs_root_volume_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ec2_key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expose_cluster_id" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "job_flow_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keep_job_flow_alive" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "managed_primary_security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "managed_replica_security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "master_instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "master_lifecycle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "release_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repo_upgrade_on_boot" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_access_security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strategy" {
  description = "(required)"
  type        = string
}

variable "task_desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "task_ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "task_instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "task_lifecycle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "task_max_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "task_min_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "task_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "termination_protected" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "visible_to_all_users" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "applications" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      args    = list(string)
      name    = string
      version = string
    }
  ))
  default = []
}

variable "bootstrap_actions_file" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket = string
      key    = string
    }
  ))
  default = []
}

variable "configurations_file" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket = string
      key    = string
    }
  ))
  default = []
}

variable "core_ebs_block_device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      iops                 = number
      size_in_gb           = number
      volume_type          = string
      volumes_per_instance = number
    }
  ))
  default = []
}

variable "core_scaling_down_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type         = string
      adjustment          = string
      cooldown            = number
      dimensions          = map(string)
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

variable "core_scaling_up_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type         = string
      adjustment          = string
      cooldown            = number
      dimensions          = map(string)
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

variable "instance_weights" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      instance_type     = string
      weighted_capacity = number
    }
  ))
  default = []
}

variable "master_ebs_block_device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      iops                 = number
      size_in_gb           = number
      volume_type          = string
      volumes_per_instance = number
    }
  ))
  default = []
}

variable "provisioning_timeout" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      timeout        = number
      timeout_action = string
    }
  ))
  default = []
}

variable "scheduled_task" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cron                = string
      desired_capacity    = string
      instance_group_type = string
      is_enabled          = bool
      max_capacity        = string
      min_capacity        = string
      task_type           = string
    }
  ))
  default = []
}

variable "steps_file" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket = string
      key    = string
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

variable "task_ebs_block_device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      iops                 = number
      size_in_gb           = number
      volume_type          = string
      volumes_per_instance = number
    }
  ))
  default = []
}

variable "task_scaling_down_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type         = string
      adjustment          = string
      cooldown            = number
      dimensions          = map(string)
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

variable "task_scaling_up_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_type         = string
      adjustment          = string
      cooldown            = number
      dimensions          = map(string)
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

variable "termination_policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      statements = list(object(
        {
          evaluation_periods = number
          metric_name        = string
          namespace          = string
          operator           = string
          period             = number
          statistic          = string
          threshold          = number
          unit               = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_mrscaler_aws" "this" {
  # additional_info - (optional) is a type of string
  additional_info = var.additional_info
  # additional_primary_security_groups - (optional) is a type of list of string
  additional_primary_security_groups = var.additional_primary_security_groups
  # additional_replica_security_groups - (optional) is a type of list of string
  additional_replica_security_groups = var.additional_replica_security_groups
  # availability_zones - (optional) is a type of list of string
  availability_zones = var.availability_zones
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # core_desired_capacity - (optional) is a type of number
  core_desired_capacity = var.core_desired_capacity
  # core_ebs_optimized - (optional) is a type of bool
  core_ebs_optimized = var.core_ebs_optimized
  # core_instance_types - (optional) is a type of list of string
  core_instance_types = var.core_instance_types
  # core_lifecycle - (optional) is a type of string
  core_lifecycle = var.core_lifecycle
  # core_max_size - (optional) is a type of number
  core_max_size = var.core_max_size
  # core_min_size - (optional) is a type of number
  core_min_size = var.core_min_size
  # core_unit - (optional) is a type of string
  core_unit = var.core_unit
  # custom_ami_id - (optional) is a type of string
  custom_ami_id = var.custom_ami_id
  # description - (optional) is a type of string
  description = var.description
  # ebs_root_volume_size - (optional) is a type of number
  ebs_root_volume_size = var.ebs_root_volume_size
  # ec2_key_name - (optional) is a type of string
  ec2_key_name = var.ec2_key_name
  # expose_cluster_id - (optional) is a type of bool
  expose_cluster_id = var.expose_cluster_id
  # job_flow_role - (optional) is a type of string
  job_flow_role = var.job_flow_role
  # keep_job_flow_alive - (optional) is a type of bool
  keep_job_flow_alive = var.keep_job_flow_alive
  # log_uri - (optional) is a type of string
  log_uri = var.log_uri
  # managed_primary_security_group - (optional) is a type of string
  managed_primary_security_group = var.managed_primary_security_group
  # managed_replica_security_group - (optional) is a type of string
  managed_replica_security_group = var.managed_replica_security_group
  # master_ebs_optimized - (optional) is a type of bool
  master_ebs_optimized = var.master_ebs_optimized
  # master_instance_types - (optional) is a type of list of string
  master_instance_types = var.master_instance_types
  # master_lifecycle - (optional) is a type of string
  master_lifecycle = var.master_lifecycle
  # name - (required) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
  # release_label - (optional) is a type of string
  release_label = var.release_label
  # repo_upgrade_on_boot - (optional) is a type of string
  repo_upgrade_on_boot = var.repo_upgrade_on_boot
  # retries - (optional) is a type of number
  retries = var.retries
  # security_config - (optional) is a type of string
  security_config = var.security_config
  # service_access_security_group - (optional) is a type of string
  service_access_security_group = var.service_access_security_group
  # service_role - (optional) is a type of string
  service_role = var.service_role
  # strategy - (required) is a type of string
  strategy = var.strategy
  # task_desired_capacity - (optional) is a type of number
  task_desired_capacity = var.task_desired_capacity
  # task_ebs_optimized - (optional) is a type of bool
  task_ebs_optimized = var.task_ebs_optimized
  # task_instance_types - (optional) is a type of list of string
  task_instance_types = var.task_instance_types
  # task_lifecycle - (optional) is a type of string
  task_lifecycle = var.task_lifecycle
  # task_max_size - (optional) is a type of number
  task_max_size = var.task_max_size
  # task_min_size - (optional) is a type of number
  task_min_size = var.task_min_size
  # task_unit - (optional) is a type of string
  task_unit = var.task_unit
  # termination_protected - (optional) is a type of bool
  termination_protected = var.termination_protected
  # visible_to_all_users - (optional) is a type of bool
  visible_to_all_users = var.visible_to_all_users

  dynamic "applications" {
    for_each = var.applications
    content {
      # args - (optional) is a type of list of string
      args = applications.value["args"]
      # name - (required) is a type of string
      name = applications.value["name"]
      # version - (optional) is a type of string
      version = applications.value["version"]
    }
  }

  dynamic "bootstrap_actions_file" {
    for_each = var.bootstrap_actions_file
    content {
      # bucket - (required) is a type of string
      bucket = bootstrap_actions_file.value["bucket"]
      # key - (required) is a type of string
      key = bootstrap_actions_file.value["key"]
    }
  }

  dynamic "configurations_file" {
    for_each = var.configurations_file
    content {
      # bucket - (required) is a type of string
      bucket = configurations_file.value["bucket"]
      # key - (required) is a type of string
      key = configurations_file.value["key"]
    }
  }

  dynamic "core_ebs_block_device" {
    for_each = var.core_ebs_block_device
    content {
      # iops - (optional) is a type of number
      iops = core_ebs_block_device.value["iops"]
      # size_in_gb - (required) is a type of number
      size_in_gb = core_ebs_block_device.value["size_in_gb"]
      # volume_type - (required) is a type of string
      volume_type = core_ebs_block_device.value["volume_type"]
      # volumes_per_instance - (optional) is a type of number
      volumes_per_instance = core_ebs_block_device.value["volumes_per_instance"]
    }
  }

  dynamic "core_scaling_down_policy" {
    for_each = var.core_scaling_down_policy
    content {
      # action_type - (optional) is a type of string
      action_type = core_scaling_down_policy.value["action_type"]
      # adjustment - (optional) is a type of string
      adjustment = core_scaling_down_policy.value["adjustment"]
      # cooldown - (optional) is a type of number
      cooldown = core_scaling_down_policy.value["cooldown"]
      # dimensions - (optional) is a type of map of string
      dimensions = core_scaling_down_policy.value["dimensions"]
      # evaluation_periods - (optional) is a type of number
      evaluation_periods = core_scaling_down_policy.value["evaluation_periods"]
      # max_target_capacity - (optional) is a type of string
      max_target_capacity = core_scaling_down_policy.value["max_target_capacity"]
      # maximum - (optional) is a type of string
      maximum = core_scaling_down_policy.value["maximum"]
      # metric_name - (required) is a type of string
      metric_name = core_scaling_down_policy.value["metric_name"]
      # min_target_capacity - (optional) is a type of string
      min_target_capacity = core_scaling_down_policy.value["min_target_capacity"]
      # minimum - (optional) is a type of string
      minimum = core_scaling_down_policy.value["minimum"]
      # namespace - (required) is a type of string
      namespace = core_scaling_down_policy.value["namespace"]
      # operator - (optional) is a type of string
      operator = core_scaling_down_policy.value["operator"]
      # period - (optional) is a type of number
      period = core_scaling_down_policy.value["period"]
      # policy_name - (required) is a type of string
      policy_name = core_scaling_down_policy.value["policy_name"]
      # statistic - (optional) is a type of string
      statistic = core_scaling_down_policy.value["statistic"]
      # target - (optional) is a type of string
      target = core_scaling_down_policy.value["target"]
      # threshold - (required) is a type of number
      threshold = core_scaling_down_policy.value["threshold"]
      # unit - (required) is a type of string
      unit = core_scaling_down_policy.value["unit"]
    }
  }

  dynamic "core_scaling_up_policy" {
    for_each = var.core_scaling_up_policy
    content {
      # action_type - (optional) is a type of string
      action_type = core_scaling_up_policy.value["action_type"]
      # adjustment - (optional) is a type of string
      adjustment = core_scaling_up_policy.value["adjustment"]
      # cooldown - (optional) is a type of number
      cooldown = core_scaling_up_policy.value["cooldown"]
      # dimensions - (optional) is a type of map of string
      dimensions = core_scaling_up_policy.value["dimensions"]
      # evaluation_periods - (optional) is a type of number
      evaluation_periods = core_scaling_up_policy.value["evaluation_periods"]
      # max_target_capacity - (optional) is a type of string
      max_target_capacity = core_scaling_up_policy.value["max_target_capacity"]
      # maximum - (optional) is a type of string
      maximum = core_scaling_up_policy.value["maximum"]
      # metric_name - (required) is a type of string
      metric_name = core_scaling_up_policy.value["metric_name"]
      # min_target_capacity - (optional) is a type of string
      min_target_capacity = core_scaling_up_policy.value["min_target_capacity"]
      # minimum - (optional) is a type of string
      minimum = core_scaling_up_policy.value["minimum"]
      # namespace - (required) is a type of string
      namespace = core_scaling_up_policy.value["namespace"]
      # operator - (optional) is a type of string
      operator = core_scaling_up_policy.value["operator"]
      # period - (optional) is a type of number
      period = core_scaling_up_policy.value["period"]
      # policy_name - (required) is a type of string
      policy_name = core_scaling_up_policy.value["policy_name"]
      # statistic - (optional) is a type of string
      statistic = core_scaling_up_policy.value["statistic"]
      # target - (optional) is a type of string
      target = core_scaling_up_policy.value["target"]
      # threshold - (required) is a type of number
      threshold = core_scaling_up_policy.value["threshold"]
      # unit - (required) is a type of string
      unit = core_scaling_up_policy.value["unit"]
    }
  }

  dynamic "instance_weights" {
    for_each = var.instance_weights
    content {
      # instance_type - (required) is a type of string
      instance_type = instance_weights.value["instance_type"]
      # weighted_capacity - (required) is a type of number
      weighted_capacity = instance_weights.value["weighted_capacity"]
    }
  }

  dynamic "master_ebs_block_device" {
    for_each = var.master_ebs_block_device
    content {
      # iops - (optional) is a type of number
      iops = master_ebs_block_device.value["iops"]
      # size_in_gb - (required) is a type of number
      size_in_gb = master_ebs_block_device.value["size_in_gb"]
      # volume_type - (required) is a type of string
      volume_type = master_ebs_block_device.value["volume_type"]
      # volumes_per_instance - (optional) is a type of number
      volumes_per_instance = master_ebs_block_device.value["volumes_per_instance"]
    }
  }

  dynamic "provisioning_timeout" {
    for_each = var.provisioning_timeout
    content {
      # timeout - (required) is a type of number
      timeout = provisioning_timeout.value["timeout"]
      # timeout_action - (required) is a type of string
      timeout_action = provisioning_timeout.value["timeout_action"]
    }
  }

  dynamic "scheduled_task" {
    for_each = var.scheduled_task
    content {
      # cron - (required) is a type of string
      cron = scheduled_task.value["cron"]
      # desired_capacity - (optional) is a type of string
      desired_capacity = scheduled_task.value["desired_capacity"]
      # instance_group_type - (required) is a type of string
      instance_group_type = scheduled_task.value["instance_group_type"]
      # is_enabled - (optional) is a type of bool
      is_enabled = scheduled_task.value["is_enabled"]
      # max_capacity - (optional) is a type of string
      max_capacity = scheduled_task.value["max_capacity"]
      # min_capacity - (optional) is a type of string
      min_capacity = scheduled_task.value["min_capacity"]
      # task_type - (required) is a type of string
      task_type = scheduled_task.value["task_type"]
    }
  }

  dynamic "steps_file" {
    for_each = var.steps_file
    content {
      # bucket - (required) is a type of string
      bucket = steps_file.value["bucket"]
      # key - (required) is a type of string
      key = steps_file.value["key"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

  dynamic "task_ebs_block_device" {
    for_each = var.task_ebs_block_device
    content {
      # iops - (optional) is a type of number
      iops = task_ebs_block_device.value["iops"]
      # size_in_gb - (required) is a type of number
      size_in_gb = task_ebs_block_device.value["size_in_gb"]
      # volume_type - (required) is a type of string
      volume_type = task_ebs_block_device.value["volume_type"]
      # volumes_per_instance - (optional) is a type of number
      volumes_per_instance = task_ebs_block_device.value["volumes_per_instance"]
    }
  }

  dynamic "task_scaling_down_policy" {
    for_each = var.task_scaling_down_policy
    content {
      # action_type - (optional) is a type of string
      action_type = task_scaling_down_policy.value["action_type"]
      # adjustment - (optional) is a type of string
      adjustment = task_scaling_down_policy.value["adjustment"]
      # cooldown - (optional) is a type of number
      cooldown = task_scaling_down_policy.value["cooldown"]
      # dimensions - (optional) is a type of map of string
      dimensions = task_scaling_down_policy.value["dimensions"]
      # evaluation_periods - (optional) is a type of number
      evaluation_periods = task_scaling_down_policy.value["evaluation_periods"]
      # max_target_capacity - (optional) is a type of string
      max_target_capacity = task_scaling_down_policy.value["max_target_capacity"]
      # maximum - (optional) is a type of string
      maximum = task_scaling_down_policy.value["maximum"]
      # metric_name - (required) is a type of string
      metric_name = task_scaling_down_policy.value["metric_name"]
      # min_target_capacity - (optional) is a type of string
      min_target_capacity = task_scaling_down_policy.value["min_target_capacity"]
      # minimum - (optional) is a type of string
      minimum = task_scaling_down_policy.value["minimum"]
      # namespace - (required) is a type of string
      namespace = task_scaling_down_policy.value["namespace"]
      # operator - (optional) is a type of string
      operator = task_scaling_down_policy.value["operator"]
      # period - (optional) is a type of number
      period = task_scaling_down_policy.value["period"]
      # policy_name - (required) is a type of string
      policy_name = task_scaling_down_policy.value["policy_name"]
      # statistic - (optional) is a type of string
      statistic = task_scaling_down_policy.value["statistic"]
      # target - (optional) is a type of string
      target = task_scaling_down_policy.value["target"]
      # threshold - (required) is a type of number
      threshold = task_scaling_down_policy.value["threshold"]
      # unit - (required) is a type of string
      unit = task_scaling_down_policy.value["unit"]
    }
  }

  dynamic "task_scaling_up_policy" {
    for_each = var.task_scaling_up_policy
    content {
      # action_type - (optional) is a type of string
      action_type = task_scaling_up_policy.value["action_type"]
      # adjustment - (optional) is a type of string
      adjustment = task_scaling_up_policy.value["adjustment"]
      # cooldown - (optional) is a type of number
      cooldown = task_scaling_up_policy.value["cooldown"]
      # dimensions - (optional) is a type of map of string
      dimensions = task_scaling_up_policy.value["dimensions"]
      # evaluation_periods - (optional) is a type of number
      evaluation_periods = task_scaling_up_policy.value["evaluation_periods"]
      # max_target_capacity - (optional) is a type of string
      max_target_capacity = task_scaling_up_policy.value["max_target_capacity"]
      # maximum - (optional) is a type of string
      maximum = task_scaling_up_policy.value["maximum"]
      # metric_name - (required) is a type of string
      metric_name = task_scaling_up_policy.value["metric_name"]
      # min_target_capacity - (optional) is a type of string
      min_target_capacity = task_scaling_up_policy.value["min_target_capacity"]
      # minimum - (optional) is a type of string
      minimum = task_scaling_up_policy.value["minimum"]
      # namespace - (required) is a type of string
      namespace = task_scaling_up_policy.value["namespace"]
      # operator - (optional) is a type of string
      operator = task_scaling_up_policy.value["operator"]
      # period - (optional) is a type of number
      period = task_scaling_up_policy.value["period"]
      # policy_name - (required) is a type of string
      policy_name = task_scaling_up_policy.value["policy_name"]
      # statistic - (optional) is a type of string
      statistic = task_scaling_up_policy.value["statistic"]
      # target - (optional) is a type of string
      target = task_scaling_up_policy.value["target"]
      # threshold - (required) is a type of number
      threshold = task_scaling_up_policy.value["threshold"]
      # unit - (required) is a type of string
      unit = task_scaling_up_policy.value["unit"]
    }
  }

  dynamic "termination_policies" {
    for_each = var.termination_policies
    content {

      dynamic "statements" {
        for_each = termination_policies.value.statements
        content {
          # evaluation_periods - (optional) is a type of number
          evaluation_periods = statements.value["evaluation_periods"]
          # metric_name - (required) is a type of string
          metric_name = statements.value["metric_name"]
          # namespace - (required) is a type of string
          namespace = statements.value["namespace"]
          # operator - (optional) is a type of string
          operator = statements.value["operator"]
          # period - (optional) is a type of number
          period = statements.value["period"]
          # statistic - (optional) is a type of string
          statistic = statements.value["statistic"]
          # threshold - (required) is a type of number
          threshold = statements.value["threshold"]
          # unit - (optional) is a type of string
          unit = statements.value["unit"]
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
  value       = spotinst_mrscaler_aws.this.id
}

output "output_cluster_id" {
  description = "returns a string"
  value       = spotinst_mrscaler_aws.this.output_cluster_id
}

output "this" {
  value = spotinst_mrscaler_aws.this
}
```

[top](#index)