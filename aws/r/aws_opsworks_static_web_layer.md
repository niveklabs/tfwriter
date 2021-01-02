# aws_opsworks_static_web_layer

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
module "aws_opsworks_static_web_layer" {
  source = "./modules/aws/r/aws_opsworks_static_web_layer"

  # auto_assign_elastic_ips - (optional) is a type of bool
  auto_assign_elastic_ips = null
  # auto_assign_public_ips - (optional) is a type of bool
  auto_assign_public_ips = null
  # auto_healing - (optional) is a type of bool
  auto_healing = null
  # custom_configure_recipes - (optional) is a type of list of string
  custom_configure_recipes = []
  # custom_deploy_recipes - (optional) is a type of list of string
  custom_deploy_recipes = []
  # custom_instance_profile_arn - (optional) is a type of string
  custom_instance_profile_arn = null
  # custom_json - (optional) is a type of string
  custom_json = null
  # custom_security_group_ids - (optional) is a type of set of string
  custom_security_group_ids = []
  # custom_setup_recipes - (optional) is a type of list of string
  custom_setup_recipes = []
  # custom_shutdown_recipes - (optional) is a type of list of string
  custom_shutdown_recipes = []
  # custom_undeploy_recipes - (optional) is a type of list of string
  custom_undeploy_recipes = []
  # drain_elb_on_shutdown - (optional) is a type of bool
  drain_elb_on_shutdown = null
  # elastic_load_balancer - (optional) is a type of string
  elastic_load_balancer = null
  # install_updates_on_boot - (optional) is a type of bool
  install_updates_on_boot = null
  # instance_shutdown_timeout - (optional) is a type of number
  instance_shutdown_timeout = null
  # name - (optional) is a type of string
  name = null
  # stack_id - (required) is a type of string
  stack_id = null
  # system_packages - (optional) is a type of set of string
  system_packages = []
  # tags - (optional) is a type of map of string
  tags = {}
  # use_ebs_optimized_instances - (optional) is a type of bool
  use_ebs_optimized_instances = null

  ebs_volume = [{
    encrypted       = null
    iops            = null
    mount_point     = null
    number_of_disks = null
    raid_level      = null
    size            = null
    type            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_assign_elastic_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_assign_public_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_healing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "custom_configure_recipes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "custom_deploy_recipes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "custom_instance_profile_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "custom_setup_recipes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "custom_shutdown_recipes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "custom_undeploy_recipes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "drain_elb_on_shutdown" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "elastic_load_balancer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "install_updates_on_boot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_shutdown_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_id" {
  description = "(required)"
  type        = string
}

variable "system_packages" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "use_ebs_optimized_instances" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ebs_volume" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      encrypted       = bool
      iops            = number
      mount_point     = string
      number_of_disks = number
      raid_level      = string
      size            = number
      type            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_opsworks_static_web_layer" "this" {
  auto_assign_elastic_ips     = var.auto_assign_elastic_ips
  auto_assign_public_ips      = var.auto_assign_public_ips
  auto_healing                = var.auto_healing
  custom_configure_recipes    = var.custom_configure_recipes
  custom_deploy_recipes       = var.custom_deploy_recipes
  custom_instance_profile_arn = var.custom_instance_profile_arn
  custom_json                 = var.custom_json
  custom_security_group_ids   = var.custom_security_group_ids
  custom_setup_recipes        = var.custom_setup_recipes
  custom_shutdown_recipes     = var.custom_shutdown_recipes
  custom_undeploy_recipes     = var.custom_undeploy_recipes
  drain_elb_on_shutdown       = var.drain_elb_on_shutdown
  elastic_load_balancer       = var.elastic_load_balancer
  install_updates_on_boot     = var.install_updates_on_boot
  instance_shutdown_timeout   = var.instance_shutdown_timeout
  name                        = var.name
  stack_id                    = var.stack_id
  system_packages             = var.system_packages
  tags                        = var.tags
  use_ebs_optimized_instances = var.use_ebs_optimized_instances

  dynamic "ebs_volume" {
    for_each = var.ebs_volume
    content {
      encrypted       = ebs_volume.value["encrypted"]
      iops            = ebs_volume.value["iops"]
      mount_point     = ebs_volume.value["mount_point"]
      number_of_disks = ebs_volume.value["number_of_disks"]
      raid_level      = ebs_volume.value["raid_level"]
      size            = ebs_volume.value["size"]
      type            = ebs_volume.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_opsworks_static_web_layer.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_opsworks_static_web_layer.this.id
}

output "this" {
  value = aws_opsworks_static_web_layer.this
}
```

[top](#index)