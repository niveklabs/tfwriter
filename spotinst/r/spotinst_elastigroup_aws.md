# spotinst_elastigroup_aws

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
module "spotinst_elastigroup_aws" {
  source = "./modules/spotinst/r/spotinst_elastigroup_aws"

  # availability_zones - (optional) is a type of list of string
  availability_zones = []
  # block_devices_mode - (optional) is a type of string
  block_devices_mode = null
  # capacity_unit - (optional) is a type of string
  capacity_unit = null
  # cpu_credits - (optional) is a type of string
  cpu_credits = null
  # description - (optional) is a type of string
  description = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # draining_timeout - (optional) is a type of number
  draining_timeout = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # elastic_ips - (optional) is a type of list of string
  elastic_ips = []
  # elastic_load_balancers - (optional) is a type of list of string
  elastic_load_balancers = []
  # enable_monitoring - (optional) is a type of bool
  enable_monitoring = null
  # fallback_to_ondemand - (required) is a type of bool
  fallback_to_ondemand = null
  # health_check_grace_period - (optional) is a type of number
  health_check_grace_period = null
  # health_check_type - (optional) is a type of string
  health_check_type = null
  # health_check_unhealthy_duration_before_replacement - (optional) is a type of number
  health_check_unhealthy_duration_before_replacement = null
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # image_id - (optional) is a type of string
  image_id = null
  # instance_types_ondemand - (required) is a type of string
  instance_types_ondemand = null
  # instance_types_preferred_spot - (optional) is a type of list of string
  instance_types_preferred_spot = []
  # instance_types_spot - (required) is a type of list of string
  instance_types_spot = []
  # key_name - (optional) is a type of string
  key_name = null
  # lifetime_period - (optional) is a type of string
  lifetime_period = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # ondemand_count - (optional) is a type of number
  ondemand_count = null
  # orientation - (required) is a type of string
  orientation = null
  # persist_block_devices - (optional) is a type of bool
  persist_block_devices = null
  # persist_private_ip - (optional) is a type of bool
  persist_private_ip = null
  # persist_root_device - (optional) is a type of bool
  persist_root_device = null
  # placement_tenancy - (optional) is a type of string
  placement_tenancy = null
  # preferred_availability_zones - (optional) is a type of list of string
  preferred_availability_zones = []
  # private_ips - (optional) is a type of list of string
  private_ips = []
  # product - (required) is a type of string
  product = null
  # region - (optional) is a type of string
  region = null
  # security_groups - (required) is a type of list of string
  security_groups = []
  # shutdown_script - (optional) is a type of string
  shutdown_script = null
  # spot_percentage - (optional) is a type of number
  spot_percentage = null
  # subnet_ids - (optional) is a type of list of string
  subnet_ids = []
  # target_group_arns - (optional) is a type of list of string
  target_group_arns = []
  # user_data - (optional) is a type of string
  user_data = null
  # utilize_reserved_instances - (optional) is a type of bool
  utilize_reserved_instances = null
  # wait_for_capacity - (optional) is a type of number
  wait_for_capacity = null
  # wait_for_capacity_timeout - (optional) is a type of number
  wait_for_capacity_timeout = null

  ebs_block_device = [{
    delete_on_termination = null
    device_name           = null
    encrypted             = null
    iops                  = null
    kms_key_id            = null
    snapshot_id           = null
    volume_size           = null
    volume_type           = null
  }]

  ephemeral_block_device = [{
    device_name  = null
    virtual_name = null
  }]

  instance_types_weights = [{
    instance_type = null
    weight        = null
  }]

  integration_beanstalk = [{
    deployment_preferences = [{
      automatic_roll        = null
      batch_size_percentage = null
      grace_period          = null
      strategy = [{
        action                 = null
        should_drain_instances = null
      }]
    }]
    environment_id = null
    managed_actions = [{
      platform_update = [{
        perform_at   = null
        time_window  = null
        update_level = null
      }]
    }]
  }]

  integration_codedeploy = [{
    cleanup_on_failure = null
    deployment_groups = [{
      application_name      = null
      deployment_group_name = null
    }]
    terminate_instance_on_failure = null
  }]

  integration_docker_swarm = [{
    autoscale_cooldown = null
    autoscale_down = [{
      evaluation_periods = null
    }]
    autoscale_headroom = [{
      cpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    autoscale_is_enabled = null
    master_host          = null
    master_port          = null
  }]

  integration_ecs = [{
    autoscale_attributes = [{
      key   = null
      value = null
    }]
    autoscale_cooldown = null
    autoscale_down = [{
      evaluation_periods        = null
      max_scale_down_percentage = null
    }]
    autoscale_headroom = [{
      cpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    autoscale_is_auto_config               = null
    autoscale_is_enabled                   = null
    autoscale_scale_down_non_service_tasks = null
    batch = [{
      job_queue_names = []
    }]
    cluster_name = null
  }]

  integration_gitlab = [{
    runner = [{
      is_enabled = null
    }]
  }]

  integration_kubernetes = [{
    api_server         = null
    autoscale_cooldown = null
    autoscale_down = [{
      evaluation_periods = null
    }]
    autoscale_headroom = [{
      cpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    autoscale_is_auto_config = null
    autoscale_is_enabled     = null
    autoscale_labels = [{
      key   = null
      value = null
    }]
    cluster_identifier = null
    integration_mode   = null
    token              = null
  }]

  integration_mesosphere = [{
    api_server = null
  }]

  integration_multai_runtime = [{
    deployment_id = null
  }]

  integration_nomad = [{
    acl_token = null
    autoscale_constraints = [{
      key   = null
      value = null
    }]
    autoscale_cooldown = null
    autoscale_down = [{
      evaluation_periods = null
    }]
    autoscale_headroom = [{
      cpu_per_unit    = null
      memory_per_unit = null
      num_of_units    = null
    }]
    autoscale_is_enabled = null
    master_host          = null
    master_port          = null
  }]

  integration_rancher = [{
    access_key  = null
    master_host = null
    secret_key  = null
    version     = null
  }]

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

  metadata_options = [{
    http_put_response_hop_limit = null
    http_tokens                 = null
  }]

  multai_target_sets = [{
    balancer_id   = null
    target_set_id = null
  }]

  network_interface = [{
    associate_ipv6_address             = null
    associate_public_ip_address        = null
    delete_on_termination              = null
    description                        = null
    device_index                       = null
    network_interface_id               = null
    private_ip_address                 = null
    secondary_private_ip_address_count = null
  }]

  revert_to_spot = [{
    perform_at   = null
    time_windows = []
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
    is_enabled          = null
    max_target_capacity = null
    maximum             = null
    metric_name         = null
    min_target_capacity = null
    minimum             = null
    namespace           = null
    operator            = null
    period              = null
    policy_name         = null
    source              = null
    statistic           = null
    target              = null
    threshold           = null
    unit                = null
  }]

  scaling_strategy = [{
    terminate_at_end_of_billing_hour = null
    termination_policy               = null
  }]

  scaling_target_policy = [{
    cooldown = null
    dimensions = [{
      name  = null
      value = null
    }]
    max_capacity_per_scale = null
    metric_name            = null
    namespace              = null
    policy_name            = null
    predictive_mode        = null
    source                 = null
    statistic              = null
    target                 = null
    unit                   = null
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
    is_enabled          = null
    max_target_capacity = null
    maximum             = null
    metric_name         = null
    min_target_capacity = null
    minimum             = null
    namespace           = null
    operator            = null
    period              = null
    policy_name         = null
    source              = null
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
    frequency             = null
    grace_period          = null
    is_enabled            = null
    max_capacity          = null
    min_capacity          = null
    scale_max_capacity    = null
    scale_min_capacity    = null
    scale_target_capacity = null
    start_time            = null
    target_capacity       = null
    task_type             = null
  }]

  signal = [{
    name    = null
    timeout = null
  }]

  stateful_deallocation = [{
    should_delete_images             = null
    should_delete_network_interfaces = null
    should_delete_snapshots          = null
    should_delete_volumes            = null
  }]

  tags = [{
    key   = null
    value = null
  }]

  update_policy = [{
    auto_apply_tags = null
    roll_config = [{
      batch_size_percentage = null
      grace_period          = null
      health_check_type     = null
      strategy = [{
        action                       = null
        batch_min_healthy_percentage = null
        on_failure = [{
          action_type                      = null
          batch_num                        = null
          draining_timeout                 = null
          should_decrement_target_capacity = null
          should_handle_all_batches        = null
        }]
        should_drain_instances = null
      }]
      wait_for_roll_percentage = null
      wait_for_roll_timeout    = null
    }]
    should_resume_stateful = null
    should_roll            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "block_devices_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capacity_unit" {
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

variable "desired_capacity" {
  description = "(optional)"
  type        = number
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

variable "elastic_ips" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "elastic_load_balancers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "enable_monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fallback_to_ondemand" {
  description = "(required)"
  type        = bool
}

variable "health_check_grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_unhealthy_duration_before_replacement" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iam_instance_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_types_ondemand" {
  description = "(required)"
  type        = string
}

variable "instance_types_preferred_spot" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_types_spot" {
  description = "(required)"
  type        = list(string)
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lifetime_period" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "ondemand_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "orientation" {
  description = "(required)"
  type        = string
}

variable "persist_block_devices" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "preferred_availability_zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "private_ips" {
  description = "(optional)"
  type        = list(string)
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

variable "security_groups" {
  description = "(required)"
  type        = list(string)
}

variable "shutdown_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "subnet_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "target_group_arns" {
  description = "(optional)"
  type        = list(string)
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

variable "wait_for_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wait_for_capacity_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ebs_block_device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      delete_on_termination = bool
      device_name           = string
      encrypted             = bool
      iops                  = number
      kms_key_id            = string
      snapshot_id           = string
      volume_size           = number
      volume_type           = string
    }
  ))
  default = []
}

variable "ephemeral_block_device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      device_name  = string
      virtual_name = string
    }
  ))
  default = []
}

variable "instance_types_weights" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      instance_type = string
      weight        = number
    }
  ))
  default = []
}

variable "integration_beanstalk" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      deployment_preferences = list(object(
        {
          automatic_roll        = bool
          batch_size_percentage = number
          grace_period          = number
          strategy = list(object(
            {
              action                 = string
              should_drain_instances = bool
            }
          ))
        }
      ))
      environment_id = string
      managed_actions = list(object(
        {
          platform_update = list(object(
            {
              perform_at   = string
              time_window  = string
              update_level = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "integration_codedeploy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cleanup_on_failure = bool
      deployment_groups = set(object(
        {
          application_name      = string
          deployment_group_name = string
        }
      ))
      terminate_instance_on_failure = bool
    }
  ))
  default = []
}

variable "integration_docker_swarm" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      autoscale_cooldown = number
      autoscale_down = list(object(
        {
          evaluation_periods = number
        }
      ))
      autoscale_headroom = list(object(
        {
          cpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      autoscale_is_enabled = bool
      master_host          = string
      master_port          = number
    }
  ))
  default = []
}

variable "integration_ecs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      autoscale_attributes = set(object(
        {
          key   = string
          value = string
        }
      ))
      autoscale_cooldown = number
      autoscale_down = list(object(
        {
          evaluation_periods        = number
          max_scale_down_percentage = number
        }
      ))
      autoscale_headroom = list(object(
        {
          cpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      autoscale_is_auto_config               = bool
      autoscale_is_enabled                   = bool
      autoscale_scale_down_non_service_tasks = bool
      batch = list(object(
        {
          job_queue_names = list(string)
        }
      ))
      cluster_name = string
    }
  ))
  default = []
}

variable "integration_gitlab" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      runner = list(object(
        {
          is_enabled = bool
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
      api_server         = string
      autoscale_cooldown = number
      autoscale_down = list(object(
        {
          evaluation_periods = number
        }
      ))
      autoscale_headroom = list(object(
        {
          cpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      autoscale_is_auto_config = bool
      autoscale_is_enabled     = bool
      autoscale_labels = set(object(
        {
          key   = string
          value = string
        }
      ))
      cluster_identifier = string
      integration_mode   = string
      token              = string
    }
  ))
  default = []
}

variable "integration_mesosphere" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      api_server = string
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

variable "integration_nomad" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      acl_token = string
      autoscale_constraints = set(object(
        {
          key   = string
          value = string
        }
      ))
      autoscale_cooldown = number
      autoscale_down = list(object(
        {
          evaluation_periods = number
        }
      ))
      autoscale_headroom = list(object(
        {
          cpu_per_unit    = number
          memory_per_unit = number
          num_of_units    = number
        }
      ))
      autoscale_is_enabled = bool
      master_host          = string
      master_port          = number
    }
  ))
  default = []
}

variable "integration_rancher" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key  = string
      master_host = string
      secret_key  = string
      version     = string
    }
  ))
  default = []
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

variable "metadata_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http_put_response_hop_limit = number
      http_tokens                 = string
    }
  ))
  default = []
}

variable "multai_target_sets" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      balancer_id   = string
      target_set_id = string
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      associate_ipv6_address             = bool
      associate_public_ip_address        = bool
      delete_on_termination              = bool
      description                        = string
      device_index                       = string
      network_interface_id               = string
      private_ip_address                 = string
      secondary_private_ip_address_count = string
    }
  ))
  default = []
}

variable "revert_to_spot" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      perform_at   = string
      time_windows = list(string)
    }
  ))
  default = []
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
      is_enabled          = bool
      max_target_capacity = string
      maximum             = string
      metric_name         = string
      min_target_capacity = string
      minimum             = string
      namespace           = string
      operator            = string
      period              = number
      policy_name         = string
      source              = string
      statistic           = string
      target              = string
      threshold           = number
      unit                = string
    }
  ))
  default = []
}

variable "scaling_strategy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      terminate_at_end_of_billing_hour = bool
      termination_policy               = string
    }
  ))
  default = []
}

variable "scaling_target_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cooldown = number
      dimensions = list(object(
        {
          name  = string
          value = string
        }
      ))
      max_capacity_per_scale = string
      metric_name            = string
      namespace              = string
      policy_name            = string
      predictive_mode        = string
      source                 = string
      statistic              = string
      target                 = number
      unit                   = string
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
      is_enabled          = bool
      max_target_capacity = string
      maximum             = string
      metric_name         = string
      min_target_capacity = string
      minimum             = string
      namespace           = string
      operator            = string
      period              = number
      policy_name         = string
      source              = string
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
      frequency             = string
      grace_period          = string
      is_enabled            = bool
      max_capacity          = string
      min_capacity          = string
      scale_max_capacity    = string
      scale_min_capacity    = string
      scale_target_capacity = string
      start_time            = string
      target_capacity       = string
      task_type             = string
    }
  ))
  default = []
}

variable "signal" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name    = string
      timeout = number
    }
  ))
  default = []
}

variable "stateful_deallocation" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      should_delete_images             = bool
      should_delete_network_interfaces = bool
      should_delete_snapshots          = bool
      should_delete_volumes            = bool
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

variable "update_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_apply_tags = bool
      roll_config = list(object(
        {
          batch_size_percentage = number
          grace_period          = number
          health_check_type     = string
          strategy = list(object(
            {
              action                       = string
              batch_min_healthy_percentage = number
              on_failure = list(object(
                {
                  action_type                      = string
                  batch_num                        = number
                  draining_timeout                 = number
                  should_decrement_target_capacity = bool
                  should_handle_all_batches        = bool
                }
              ))
              should_drain_instances = bool
            }
          ))
          wait_for_roll_percentage = number
          wait_for_roll_timeout    = number
        }
      ))
      should_resume_stateful = bool
      should_roll            = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_elastigroup_aws" "this" {
  availability_zones                                 = var.availability_zones
  block_devices_mode                                 = var.block_devices_mode
  capacity_unit                                      = var.capacity_unit
  cpu_credits                                        = var.cpu_credits
  description                                        = var.description
  desired_capacity                                   = var.desired_capacity
  draining_timeout                                   = var.draining_timeout
  ebs_optimized                                      = var.ebs_optimized
  elastic_ips                                        = var.elastic_ips
  elastic_load_balancers                             = var.elastic_load_balancers
  enable_monitoring                                  = var.enable_monitoring
  fallback_to_ondemand                               = var.fallback_to_ondemand
  health_check_grace_period                          = var.health_check_grace_period
  health_check_type                                  = var.health_check_type
  health_check_unhealthy_duration_before_replacement = var.health_check_unhealthy_duration_before_replacement
  iam_instance_profile                               = var.iam_instance_profile
  image_id                                           = var.image_id
  instance_types_ondemand                            = var.instance_types_ondemand
  instance_types_preferred_spot                      = var.instance_types_preferred_spot
  instance_types_spot                                = var.instance_types_spot
  key_name                                           = var.key_name
  lifetime_period                                    = var.lifetime_period
  max_size                                           = var.max_size
  min_size                                           = var.min_size
  name                                               = var.name
  ondemand_count                                     = var.ondemand_count
  orientation                                        = var.orientation
  persist_block_devices                              = var.persist_block_devices
  persist_private_ip                                 = var.persist_private_ip
  persist_root_device                                = var.persist_root_device
  placement_tenancy                                  = var.placement_tenancy
  preferred_availability_zones                       = var.preferred_availability_zones
  private_ips                                        = var.private_ips
  product                                            = var.product
  region                                             = var.region
  security_groups                                    = var.security_groups
  shutdown_script                                    = var.shutdown_script
  spot_percentage                                    = var.spot_percentage
  subnet_ids                                         = var.subnet_ids
  target_group_arns                                  = var.target_group_arns
  user_data                                          = var.user_data
  utilize_reserved_instances                         = var.utilize_reserved_instances
  wait_for_capacity                                  = var.wait_for_capacity
  wait_for_capacity_timeout                          = var.wait_for_capacity_timeout

  dynamic "ebs_block_device" {
    for_each = var.ebs_block_device
    content {
      delete_on_termination = ebs_block_device.value["delete_on_termination"]
      device_name           = ebs_block_device.value["device_name"]
      encrypted             = ebs_block_device.value["encrypted"]
      iops                  = ebs_block_device.value["iops"]
      kms_key_id            = ebs_block_device.value["kms_key_id"]
      snapshot_id           = ebs_block_device.value["snapshot_id"]
      volume_size           = ebs_block_device.value["volume_size"]
      volume_type           = ebs_block_device.value["volume_type"]
    }
  }

  dynamic "ephemeral_block_device" {
    for_each = var.ephemeral_block_device
    content {
      device_name  = ephemeral_block_device.value["device_name"]
      virtual_name = ephemeral_block_device.value["virtual_name"]
    }
  }

  dynamic "instance_types_weights" {
    for_each = var.instance_types_weights
    content {
      instance_type = instance_types_weights.value["instance_type"]
      weight        = instance_types_weights.value["weight"]
    }
  }

  dynamic "integration_beanstalk" {
    for_each = var.integration_beanstalk
    content {
      environment_id = integration_beanstalk.value["environment_id"]

      dynamic "deployment_preferences" {
        for_each = integration_beanstalk.value.deployment_preferences
        content {
          automatic_roll        = deployment_preferences.value["automatic_roll"]
          batch_size_percentage = deployment_preferences.value["batch_size_percentage"]
          grace_period          = deployment_preferences.value["grace_period"]

          dynamic "strategy" {
            for_each = deployment_preferences.value.strategy
            content {
              action                 = strategy.value["action"]
              should_drain_instances = strategy.value["should_drain_instances"]
            }
          }

        }
      }

      dynamic "managed_actions" {
        for_each = integration_beanstalk.value.managed_actions
        content {

          dynamic "platform_update" {
            for_each = managed_actions.value.platform_update
            content {
              perform_at   = platform_update.value["perform_at"]
              time_window  = platform_update.value["time_window"]
              update_level = platform_update.value["update_level"]
            }
          }

        }
      }

    }
  }

  dynamic "integration_codedeploy" {
    for_each = var.integration_codedeploy
    content {
      cleanup_on_failure            = integration_codedeploy.value["cleanup_on_failure"]
      terminate_instance_on_failure = integration_codedeploy.value["terminate_instance_on_failure"]

      dynamic "deployment_groups" {
        for_each = integration_codedeploy.value.deployment_groups
        content {
          application_name      = deployment_groups.value["application_name"]
          deployment_group_name = deployment_groups.value["deployment_group_name"]
        }
      }

    }
  }

  dynamic "integration_docker_swarm" {
    for_each = var.integration_docker_swarm
    content {
      autoscale_cooldown   = integration_docker_swarm.value["autoscale_cooldown"]
      autoscale_is_enabled = integration_docker_swarm.value["autoscale_is_enabled"]
      master_host          = integration_docker_swarm.value["master_host"]
      master_port          = integration_docker_swarm.value["master_port"]

      dynamic "autoscale_down" {
        for_each = integration_docker_swarm.value.autoscale_down
        content {
          evaluation_periods = autoscale_down.value["evaluation_periods"]
        }
      }

      dynamic "autoscale_headroom" {
        for_each = integration_docker_swarm.value.autoscale_headroom
        content {
          cpu_per_unit    = autoscale_headroom.value["cpu_per_unit"]
          memory_per_unit = autoscale_headroom.value["memory_per_unit"]
          num_of_units    = autoscale_headroom.value["num_of_units"]
        }
      }

    }
  }

  dynamic "integration_ecs" {
    for_each = var.integration_ecs
    content {
      autoscale_cooldown                     = integration_ecs.value["autoscale_cooldown"]
      autoscale_is_auto_config               = integration_ecs.value["autoscale_is_auto_config"]
      autoscale_is_enabled                   = integration_ecs.value["autoscale_is_enabled"]
      autoscale_scale_down_non_service_tasks = integration_ecs.value["autoscale_scale_down_non_service_tasks"]
      cluster_name                           = integration_ecs.value["cluster_name"]

      dynamic "autoscale_attributes" {
        for_each = integration_ecs.value.autoscale_attributes
        content {
          key   = autoscale_attributes.value["key"]
          value = autoscale_attributes.value["value"]
        }
      }

      dynamic "autoscale_down" {
        for_each = integration_ecs.value.autoscale_down
        content {
          evaluation_periods        = autoscale_down.value["evaluation_periods"]
          max_scale_down_percentage = autoscale_down.value["max_scale_down_percentage"]
        }
      }

      dynamic "autoscale_headroom" {
        for_each = integration_ecs.value.autoscale_headroom
        content {
          cpu_per_unit    = autoscale_headroom.value["cpu_per_unit"]
          memory_per_unit = autoscale_headroom.value["memory_per_unit"]
          num_of_units    = autoscale_headroom.value["num_of_units"]
        }
      }

      dynamic "batch" {
        for_each = integration_ecs.value.batch
        content {
          job_queue_names = batch.value["job_queue_names"]
        }
      }

    }
  }

  dynamic "integration_gitlab" {
    for_each = var.integration_gitlab
    content {

      dynamic "runner" {
        for_each = integration_gitlab.value.runner
        content {
          is_enabled = runner.value["is_enabled"]
        }
      }

    }
  }

  dynamic "integration_kubernetes" {
    for_each = var.integration_kubernetes
    content {
      api_server               = integration_kubernetes.value["api_server"]
      autoscale_cooldown       = integration_kubernetes.value["autoscale_cooldown"]
      autoscale_is_auto_config = integration_kubernetes.value["autoscale_is_auto_config"]
      autoscale_is_enabled     = integration_kubernetes.value["autoscale_is_enabled"]
      cluster_identifier       = integration_kubernetes.value["cluster_identifier"]
      integration_mode         = integration_kubernetes.value["integration_mode"]
      token                    = integration_kubernetes.value["token"]

      dynamic "autoscale_down" {
        for_each = integration_kubernetes.value.autoscale_down
        content {
          evaluation_periods = autoscale_down.value["evaluation_periods"]
        }
      }

      dynamic "autoscale_headroom" {
        for_each = integration_kubernetes.value.autoscale_headroom
        content {
          cpu_per_unit    = autoscale_headroom.value["cpu_per_unit"]
          memory_per_unit = autoscale_headroom.value["memory_per_unit"]
          num_of_units    = autoscale_headroom.value["num_of_units"]
        }
      }

      dynamic "autoscale_labels" {
        for_each = integration_kubernetes.value.autoscale_labels
        content {
          key   = autoscale_labels.value["key"]
          value = autoscale_labels.value["value"]
        }
      }

    }
  }

  dynamic "integration_mesosphere" {
    for_each = var.integration_mesosphere
    content {
      api_server = integration_mesosphere.value["api_server"]
    }
  }

  dynamic "integration_multai_runtime" {
    for_each = var.integration_multai_runtime
    content {
      deployment_id = integration_multai_runtime.value["deployment_id"]
    }
  }

  dynamic "integration_nomad" {
    for_each = var.integration_nomad
    content {
      acl_token            = integration_nomad.value["acl_token"]
      autoscale_cooldown   = integration_nomad.value["autoscale_cooldown"]
      autoscale_is_enabled = integration_nomad.value["autoscale_is_enabled"]
      master_host          = integration_nomad.value["master_host"]
      master_port          = integration_nomad.value["master_port"]

      dynamic "autoscale_constraints" {
        for_each = integration_nomad.value.autoscale_constraints
        content {
          key   = autoscale_constraints.value["key"]
          value = autoscale_constraints.value["value"]
        }
      }

      dynamic "autoscale_down" {
        for_each = integration_nomad.value.autoscale_down
        content {
          evaluation_periods = autoscale_down.value["evaluation_periods"]
        }
      }

      dynamic "autoscale_headroom" {
        for_each = integration_nomad.value.autoscale_headroom
        content {
          cpu_per_unit    = autoscale_headroom.value["cpu_per_unit"]
          memory_per_unit = autoscale_headroom.value["memory_per_unit"]
          num_of_units    = autoscale_headroom.value["num_of_units"]
        }
      }

    }
  }

  dynamic "integration_rancher" {
    for_each = var.integration_rancher
    content {
      access_key  = integration_rancher.value["access_key"]
      master_host = integration_rancher.value["master_host"]
      secret_key  = integration_rancher.value["secret_key"]
      version     = integration_rancher.value["version"]
    }
  }

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

  dynamic "metadata_options" {
    for_each = var.metadata_options
    content {
      http_put_response_hop_limit = metadata_options.value["http_put_response_hop_limit"]
      http_tokens                 = metadata_options.value["http_tokens"]
    }
  }

  dynamic "multai_target_sets" {
    for_each = var.multai_target_sets
    content {
      balancer_id   = multai_target_sets.value["balancer_id"]
      target_set_id = multai_target_sets.value["target_set_id"]
    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      associate_ipv6_address             = network_interface.value["associate_ipv6_address"]
      associate_public_ip_address        = network_interface.value["associate_public_ip_address"]
      delete_on_termination              = network_interface.value["delete_on_termination"]
      description                        = network_interface.value["description"]
      device_index                       = network_interface.value["device_index"]
      network_interface_id               = network_interface.value["network_interface_id"]
      private_ip_address                 = network_interface.value["private_ip_address"]
      secondary_private_ip_address_count = network_interface.value["secondary_private_ip_address_count"]
    }
  }

  dynamic "revert_to_spot" {
    for_each = var.revert_to_spot
    content {
      perform_at   = revert_to_spot.value["perform_at"]
      time_windows = revert_to_spot.value["time_windows"]
    }
  }

  dynamic "scaling_down_policy" {
    for_each = var.scaling_down_policy
    content {
      action_type         = scaling_down_policy.value["action_type"]
      adjustment          = scaling_down_policy.value["adjustment"]
      cooldown            = scaling_down_policy.value["cooldown"]
      evaluation_periods  = scaling_down_policy.value["evaluation_periods"]
      is_enabled          = scaling_down_policy.value["is_enabled"]
      max_target_capacity = scaling_down_policy.value["max_target_capacity"]
      maximum             = scaling_down_policy.value["maximum"]
      metric_name         = scaling_down_policy.value["metric_name"]
      min_target_capacity = scaling_down_policy.value["min_target_capacity"]
      minimum             = scaling_down_policy.value["minimum"]
      namespace           = scaling_down_policy.value["namespace"]
      operator            = scaling_down_policy.value["operator"]
      period              = scaling_down_policy.value["period"]
      policy_name         = scaling_down_policy.value["policy_name"]
      source              = scaling_down_policy.value["source"]
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

  dynamic "scaling_strategy" {
    for_each = var.scaling_strategy
    content {
      terminate_at_end_of_billing_hour = scaling_strategy.value["terminate_at_end_of_billing_hour"]
      termination_policy               = scaling_strategy.value["termination_policy"]
    }
  }

  dynamic "scaling_target_policy" {
    for_each = var.scaling_target_policy
    content {
      cooldown               = scaling_target_policy.value["cooldown"]
      max_capacity_per_scale = scaling_target_policy.value["max_capacity_per_scale"]
      metric_name            = scaling_target_policy.value["metric_name"]
      namespace              = scaling_target_policy.value["namespace"]
      policy_name            = scaling_target_policy.value["policy_name"]
      predictive_mode        = scaling_target_policy.value["predictive_mode"]
      source                 = scaling_target_policy.value["source"]
      statistic              = scaling_target_policy.value["statistic"]
      target                 = scaling_target_policy.value["target"]
      unit                   = scaling_target_policy.value["unit"]

      dynamic "dimensions" {
        for_each = scaling_target_policy.value.dimensions
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
      is_enabled          = scaling_up_policy.value["is_enabled"]
      max_target_capacity = scaling_up_policy.value["max_target_capacity"]
      maximum             = scaling_up_policy.value["maximum"]
      metric_name         = scaling_up_policy.value["metric_name"]
      min_target_capacity = scaling_up_policy.value["min_target_capacity"]
      minimum             = scaling_up_policy.value["minimum"]
      namespace           = scaling_up_policy.value["namespace"]
      operator            = scaling_up_policy.value["operator"]
      period              = scaling_up_policy.value["period"]
      policy_name         = scaling_up_policy.value["policy_name"]
      source              = scaling_up_policy.value["source"]
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
      frequency             = scheduled_task.value["frequency"]
      grace_period          = scheduled_task.value["grace_period"]
      is_enabled            = scheduled_task.value["is_enabled"]
      max_capacity          = scheduled_task.value["max_capacity"]
      min_capacity          = scheduled_task.value["min_capacity"]
      scale_max_capacity    = scheduled_task.value["scale_max_capacity"]
      scale_min_capacity    = scheduled_task.value["scale_min_capacity"]
      scale_target_capacity = scheduled_task.value["scale_target_capacity"]
      start_time            = scheduled_task.value["start_time"]
      target_capacity       = scheduled_task.value["target_capacity"]
      task_type             = scheduled_task.value["task_type"]
    }
  }

  dynamic "signal" {
    for_each = var.signal
    content {
      name    = signal.value["name"]
      timeout = signal.value["timeout"]
    }
  }

  dynamic "stateful_deallocation" {
    for_each = var.stateful_deallocation
    content {
      should_delete_images             = stateful_deallocation.value["should_delete_images"]
      should_delete_network_interfaces = stateful_deallocation.value["should_delete_network_interfaces"]
      should_delete_snapshots          = stateful_deallocation.value["should_delete_snapshots"]
      should_delete_volumes            = stateful_deallocation.value["should_delete_volumes"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      key   = tags.value["key"]
      value = tags.value["value"]
    }
  }

  dynamic "update_policy" {
    for_each = var.update_policy
    content {
      auto_apply_tags        = update_policy.value["auto_apply_tags"]
      should_resume_stateful = update_policy.value["should_resume_stateful"]
      should_roll            = update_policy.value["should_roll"]

      dynamic "roll_config" {
        for_each = update_policy.value.roll_config
        content {
          batch_size_percentage    = roll_config.value["batch_size_percentage"]
          grace_period             = roll_config.value["grace_period"]
          health_check_type        = roll_config.value["health_check_type"]
          wait_for_roll_percentage = roll_config.value["wait_for_roll_percentage"]
          wait_for_roll_timeout    = roll_config.value["wait_for_roll_timeout"]

          dynamic "strategy" {
            for_each = roll_config.value.strategy
            content {
              action                       = strategy.value["action"]
              batch_min_healthy_percentage = strategy.value["batch_min_healthy_percentage"]
              should_drain_instances       = strategy.value["should_drain_instances"]

              dynamic "on_failure" {
                for_each = strategy.value.on_failure
                content {
                  action_type                      = on_failure.value["action_type"]
                  batch_num                        = on_failure.value["batch_num"]
                  draining_timeout                 = on_failure.value["draining_timeout"]
                  should_decrement_target_capacity = on_failure.value["should_decrement_target_capacity"]
                  should_handle_all_batches        = on_failure.value["should_handle_all_batches"]
                }
              }

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

```terraform
output "capacity_unit" {
  description = "returns a string"
  value       = spotinst_elastigroup_aws.this.capacity_unit
}

output "draining_timeout" {
  description = "returns a number"
  value       = spotinst_elastigroup_aws.this.draining_timeout
}

output "ebs_optimized" {
  description = "returns a bool"
  value       = spotinst_elastigroup_aws.this.ebs_optimized
}

output "id" {
  description = "returns a string"
  value       = spotinst_elastigroup_aws.this.id
}

output "max_size" {
  description = "returns a number"
  value       = spotinst_elastigroup_aws.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = spotinst_elastigroup_aws.this.min_size
}

output "this" {
  value = spotinst_elastigroup_aws.this
}
```

[top](#index)