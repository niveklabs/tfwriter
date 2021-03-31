# aws_emr_cluster

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
module "aws_emr_cluster" {
  source = "./modules/aws/r/aws_emr_cluster"

  # additional_info - (optional) is a type of string
  additional_info = null
  # applications - (optional) is a type of set of string
  applications = []
  # autoscaling_role - (optional) is a type of string
  autoscaling_role = null
  # configurations - (optional) is a type of string
  configurations = null
  # configurations_json - (optional) is a type of string
  configurations_json = null
  # custom_ami_id - (optional) is a type of string
  custom_ami_id = null
  # ebs_root_volume_size - (optional) is a type of number
  ebs_root_volume_size = null
  # keep_job_flow_alive_when_no_steps - (optional) is a type of bool
  keep_job_flow_alive_when_no_steps = null
  # log_uri - (optional) is a type of string
  log_uri = null
  # name - (required) is a type of string
  name = null
  # release_label - (required) is a type of string
  release_label = null
  # scale_down_behavior - (optional) is a type of string
  scale_down_behavior = null
  # security_configuration - (optional) is a type of string
  security_configuration = null
  # service_role - (required) is a type of string
  service_role = null
  # step - (optional) is a type of list of object
  step = [{
    action_on_failure = null
    hadoop_jar_step = [{
      args       = []
      jar        = null
      main_class = null
      properties = {}
    }]
    name = null
  }]
  # step_concurrency_level - (optional) is a type of number
  step_concurrency_level = null
  # tags - (optional) is a type of map of string
  tags = {}
  # termination_protection - (optional) is a type of bool
  termination_protection = null
  # visible_to_all_users - (optional) is a type of bool
  visible_to_all_users = null

  bootstrap_action = [{
    args = []
    name = null
    path = null
  }]

  core_instance_fleet = [{
    id = null
    instance_type_configs = [{
      bid_price                                  = null
      bid_price_as_percentage_of_on_demand_price = null
      configurations = [{
        classification = null
        properties     = {}
      }]
      ebs_config = [{
        iops                 = null
        size                 = null
        type                 = null
        volumes_per_instance = null
      }]
      instance_type     = null
      weighted_capacity = null
    }]
    launch_specifications = [{
      on_demand_specification = [{
        allocation_strategy = null
      }]
      spot_specification = [{
        allocation_strategy      = null
        block_duration_minutes   = null
        timeout_action           = null
        timeout_duration_minutes = null
      }]
    }]
    name                           = null
    provisioned_on_demand_capacity = null
    provisioned_spot_capacity      = null
    target_on_demand_capacity      = null
    target_spot_capacity           = null
  }]

  core_instance_group = [{
    autoscaling_policy = null
    bid_price          = null
    ebs_config = [{
      iops                 = null
      size                 = null
      type                 = null
      volumes_per_instance = null
    }]
    id             = null
    instance_count = null
    instance_type  = null
    name           = null
  }]

  ec2_attributes = [{
    additional_master_security_groups = null
    additional_slave_security_groups  = null
    emr_managed_master_security_group = null
    emr_managed_slave_security_group  = null
    instance_profile                  = null
    key_name                          = null
    service_access_security_group     = null
    subnet_id                         = null
  }]

  kerberos_attributes = [{
    ad_domain_join_password              = null
    ad_domain_join_user                  = null
    cross_realm_trust_principal_password = null
    kdc_admin_password                   = null
    realm                                = null
  }]

  master_instance_fleet = [{
    id = null
    instance_type_configs = [{
      bid_price                                  = null
      bid_price_as_percentage_of_on_demand_price = null
      configurations = [{
        classification = null
        properties     = {}
      }]
      ebs_config = [{
        iops                 = null
        size                 = null
        type                 = null
        volumes_per_instance = null
      }]
      instance_type     = null
      weighted_capacity = null
    }]
    launch_specifications = [{
      on_demand_specification = [{
        allocation_strategy = null
      }]
      spot_specification = [{
        allocation_strategy      = null
        block_duration_minutes   = null
        timeout_action           = null
        timeout_duration_minutes = null
      }]
    }]
    name                           = null
    provisioned_on_demand_capacity = null
    provisioned_spot_capacity      = null
    target_on_demand_capacity      = null
    target_spot_capacity           = null
  }]

  master_instance_group = [{
    bid_price = null
    ebs_config = [{
      iops                 = null
      size                 = null
      type                 = null
      volumes_per_instance = null
    }]
    id             = null
    instance_count = null
    instance_type  = null
    name           = null
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

variable "applications" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "autoscaling_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configurations" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configurations_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_ami_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebs_root_volume_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keep_job_flow_alive_when_no_steps" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "release_label" {
  description = "(required)"
  type        = string
}

variable "scale_down_behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_role" {
  description = "(required)"
  type        = string
}

variable "step" {
  description = "(optional)"
  type = list(object(
    {
      action_on_failure = string
      hadoop_jar_step = list(object(
        {
          args       = list(string)
          jar        = string
          main_class = string
          properties = map(string)
        }
      ))
      name = string
    }
  ))
  default = null
}

variable "step_concurrency_level" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "termination_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "visible_to_all_users" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bootstrap_action" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      args = list(string)
      name = string
      path = string
    }
  ))
  default = []
}

variable "core_instance_fleet" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id = string
      instance_type_configs = set(object(
        {
          bid_price                                  = string
          bid_price_as_percentage_of_on_demand_price = number
          configurations = set(object(
            {
              classification = string
              properties     = map(string)
            }
          ))
          ebs_config = set(object(
            {
              iops                 = number
              size                 = number
              type                 = string
              volumes_per_instance = number
            }
          ))
          instance_type     = string
          weighted_capacity = number
        }
      ))
      launch_specifications = list(object(
        {
          on_demand_specification = list(object(
            {
              allocation_strategy = string
            }
          ))
          spot_specification = list(object(
            {
              allocation_strategy      = string
              block_duration_minutes   = number
              timeout_action           = string
              timeout_duration_minutes = number
            }
          ))
        }
      ))
      name                           = string
      provisioned_on_demand_capacity = number
      provisioned_spot_capacity      = number
      target_on_demand_capacity      = number
      target_spot_capacity           = number
    }
  ))
  default = []
}

variable "core_instance_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      autoscaling_policy = string
      bid_price          = string
      ebs_config = set(object(
        {
          iops                 = number
          size                 = number
          type                 = string
          volumes_per_instance = number
        }
      ))
      id             = string
      instance_count = number
      instance_type  = string
      name           = string
    }
  ))
  default = []
}

variable "ec2_attributes" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      additional_master_security_groups = string
      additional_slave_security_groups  = string
      emr_managed_master_security_group = string
      emr_managed_slave_security_group  = string
      instance_profile                  = string
      key_name                          = string
      service_access_security_group     = string
      subnet_id                         = string
    }
  ))
  default = []
}

variable "kerberos_attributes" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ad_domain_join_password              = string
      ad_domain_join_user                  = string
      cross_realm_trust_principal_password = string
      kdc_admin_password                   = string
      realm                                = string
    }
  ))
  default = []
}

variable "master_instance_fleet" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id = string
      instance_type_configs = set(object(
        {
          bid_price                                  = string
          bid_price_as_percentage_of_on_demand_price = number
          configurations = set(object(
            {
              classification = string
              properties     = map(string)
            }
          ))
          ebs_config = set(object(
            {
              iops                 = number
              size                 = number
              type                 = string
              volumes_per_instance = number
            }
          ))
          instance_type     = string
          weighted_capacity = number
        }
      ))
      launch_specifications = list(object(
        {
          on_demand_specification = list(object(
            {
              allocation_strategy = string
            }
          ))
          spot_specification = list(object(
            {
              allocation_strategy      = string
              block_duration_minutes   = number
              timeout_action           = string
              timeout_duration_minutes = number
            }
          ))
        }
      ))
      name                           = string
      provisioned_on_demand_capacity = number
      provisioned_spot_capacity      = number
      target_on_demand_capacity      = number
      target_spot_capacity           = number
    }
  ))
  default = []
}

variable "master_instance_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bid_price = string
      ebs_config = set(object(
        {
          iops                 = number
          size                 = number
          type                 = string
          volumes_per_instance = number
        }
      ))
      id             = string
      instance_count = number
      instance_type  = string
      name           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_emr_cluster" "this" {
  additional_info                   = var.additional_info
  applications                      = var.applications
  autoscaling_role                  = var.autoscaling_role
  configurations                    = var.configurations
  configurations_json               = var.configurations_json
  custom_ami_id                     = var.custom_ami_id
  ebs_root_volume_size              = var.ebs_root_volume_size
  keep_job_flow_alive_when_no_steps = var.keep_job_flow_alive_when_no_steps
  log_uri                           = var.log_uri
  name                              = var.name
  release_label                     = var.release_label
  scale_down_behavior               = var.scale_down_behavior
  security_configuration            = var.security_configuration
  service_role                      = var.service_role
  step                              = var.step
  step_concurrency_level            = var.step_concurrency_level
  tags                              = var.tags
  termination_protection            = var.termination_protection
  visible_to_all_users              = var.visible_to_all_users

  dynamic "bootstrap_action" {
    for_each = var.bootstrap_action
    content {
      args = bootstrap_action.value["args"]
      name = bootstrap_action.value["name"]
      path = bootstrap_action.value["path"]
    }
  }

  dynamic "core_instance_fleet" {
    for_each = var.core_instance_fleet
    content {
      name                      = core_instance_fleet.value["name"]
      target_on_demand_capacity = core_instance_fleet.value["target_on_demand_capacity"]
      target_spot_capacity      = core_instance_fleet.value["target_spot_capacity"]

      dynamic "instance_type_configs" {
        for_each = core_instance_fleet.value.instance_type_configs
        content {
          bid_price                                  = instance_type_configs.value["bid_price"]
          bid_price_as_percentage_of_on_demand_price = instance_type_configs.value["bid_price_as_percentage_of_on_demand_price"]
          instance_type                              = instance_type_configs.value["instance_type"]
          weighted_capacity                          = instance_type_configs.value["weighted_capacity"]

          dynamic "configurations" {
            for_each = instance_type_configs.value.configurations
            content {
              classification = configurations.value["classification"]
              properties     = configurations.value["properties"]
            }
          }

          dynamic "ebs_config" {
            for_each = instance_type_configs.value.ebs_config
            content {
              iops                 = ebs_config.value["iops"]
              size                 = ebs_config.value["size"]
              type                 = ebs_config.value["type"]
              volumes_per_instance = ebs_config.value["volumes_per_instance"]
            }
          }

        }
      }

      dynamic "launch_specifications" {
        for_each = core_instance_fleet.value.launch_specifications
        content {

          dynamic "on_demand_specification" {
            for_each = launch_specifications.value.on_demand_specification
            content {
              allocation_strategy = on_demand_specification.value["allocation_strategy"]
            }
          }

          dynamic "spot_specification" {
            for_each = launch_specifications.value.spot_specification
            content {
              allocation_strategy      = spot_specification.value["allocation_strategy"]
              block_duration_minutes   = spot_specification.value["block_duration_minutes"]
              timeout_action           = spot_specification.value["timeout_action"]
              timeout_duration_minutes = spot_specification.value["timeout_duration_minutes"]
            }
          }

        }
      }

    }
  }

  dynamic "core_instance_group" {
    for_each = var.core_instance_group
    content {
      autoscaling_policy = core_instance_group.value["autoscaling_policy"]
      bid_price          = core_instance_group.value["bid_price"]
      instance_count     = core_instance_group.value["instance_count"]
      instance_type      = core_instance_group.value["instance_type"]
      name               = core_instance_group.value["name"]

      dynamic "ebs_config" {
        for_each = core_instance_group.value.ebs_config
        content {
          iops                 = ebs_config.value["iops"]
          size                 = ebs_config.value["size"]
          type                 = ebs_config.value["type"]
          volumes_per_instance = ebs_config.value["volumes_per_instance"]
        }
      }

    }
  }

  dynamic "ec2_attributes" {
    for_each = var.ec2_attributes
    content {
      additional_master_security_groups = ec2_attributes.value["additional_master_security_groups"]
      additional_slave_security_groups  = ec2_attributes.value["additional_slave_security_groups"]
      emr_managed_master_security_group = ec2_attributes.value["emr_managed_master_security_group"]
      emr_managed_slave_security_group  = ec2_attributes.value["emr_managed_slave_security_group"]
      instance_profile                  = ec2_attributes.value["instance_profile"]
      key_name                          = ec2_attributes.value["key_name"]
      service_access_security_group     = ec2_attributes.value["service_access_security_group"]
      subnet_id                         = ec2_attributes.value["subnet_id"]
    }
  }

  dynamic "kerberos_attributes" {
    for_each = var.kerberos_attributes
    content {
      ad_domain_join_password              = kerberos_attributes.value["ad_domain_join_password"]
      ad_domain_join_user                  = kerberos_attributes.value["ad_domain_join_user"]
      cross_realm_trust_principal_password = kerberos_attributes.value["cross_realm_trust_principal_password"]
      kdc_admin_password                   = kerberos_attributes.value["kdc_admin_password"]
      realm                                = kerberos_attributes.value["realm"]
    }
  }

  dynamic "master_instance_fleet" {
    for_each = var.master_instance_fleet
    content {
      name                      = master_instance_fleet.value["name"]
      target_on_demand_capacity = master_instance_fleet.value["target_on_demand_capacity"]
      target_spot_capacity      = master_instance_fleet.value["target_spot_capacity"]

      dynamic "instance_type_configs" {
        for_each = master_instance_fleet.value.instance_type_configs
        content {
          bid_price                                  = instance_type_configs.value["bid_price"]
          bid_price_as_percentage_of_on_demand_price = instance_type_configs.value["bid_price_as_percentage_of_on_demand_price"]
          instance_type                              = instance_type_configs.value["instance_type"]
          weighted_capacity                          = instance_type_configs.value["weighted_capacity"]

          dynamic "configurations" {
            for_each = instance_type_configs.value.configurations
            content {
              classification = configurations.value["classification"]
              properties     = configurations.value["properties"]
            }
          }

          dynamic "ebs_config" {
            for_each = instance_type_configs.value.ebs_config
            content {
              iops                 = ebs_config.value["iops"]
              size                 = ebs_config.value["size"]
              type                 = ebs_config.value["type"]
              volumes_per_instance = ebs_config.value["volumes_per_instance"]
            }
          }

        }
      }

      dynamic "launch_specifications" {
        for_each = master_instance_fleet.value.launch_specifications
        content {

          dynamic "on_demand_specification" {
            for_each = launch_specifications.value.on_demand_specification
            content {
              allocation_strategy = on_demand_specification.value["allocation_strategy"]
            }
          }

          dynamic "spot_specification" {
            for_each = launch_specifications.value.spot_specification
            content {
              allocation_strategy      = spot_specification.value["allocation_strategy"]
              block_duration_minutes   = spot_specification.value["block_duration_minutes"]
              timeout_action           = spot_specification.value["timeout_action"]
              timeout_duration_minutes = spot_specification.value["timeout_duration_minutes"]
            }
          }

        }
      }

    }
  }

  dynamic "master_instance_group" {
    for_each = var.master_instance_group
    content {
      bid_price      = master_instance_group.value["bid_price"]
      instance_count = master_instance_group.value["instance_count"]
      instance_type  = master_instance_group.value["instance_type"]
      name           = master_instance_group.value["name"]

      dynamic "ebs_config" {
        for_each = master_instance_group.value.ebs_config
        content {
          iops                 = ebs_config.value["iops"]
          size                 = ebs_config.value["size"]
          type                 = ebs_config.value["type"]
          volumes_per_instance = ebs_config.value["volumes_per_instance"]
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
  value       = aws_emr_cluster.this.arn
}

output "cluster_state" {
  description = "returns a string"
  value       = aws_emr_cluster.this.cluster_state
}

output "id" {
  description = "returns a string"
  value       = aws_emr_cluster.this.id
}

output "keep_job_flow_alive_when_no_steps" {
  description = "returns a bool"
  value       = aws_emr_cluster.this.keep_job_flow_alive_when_no_steps
}

output "master_public_dns" {
  description = "returns a string"
  value       = aws_emr_cluster.this.master_public_dns
}

output "scale_down_behavior" {
  description = "returns a string"
  value       = aws_emr_cluster.this.scale_down_behavior
}

output "step" {
  description = "returns a list of object"
  value       = aws_emr_cluster.this.step
}

output "termination_protection" {
  description = "returns a bool"
  value       = aws_emr_cluster.this.termination_protection
}

output "this" {
  value = aws_emr_cluster.this
}
```

[top](#index)