# aws_launch_template

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
module "aws_launch_template" {
  source = "./modules/aws/r/aws_launch_template"

  # default_version - (optional) is a type of number
  default_version = null
  # description - (optional) is a type of string
  description = null
  # disable_api_termination - (optional) is a type of bool
  disable_api_termination = null
  # ebs_optimized - (optional) is a type of string
  ebs_optimized = null
  # image_id - (optional) is a type of string
  image_id = null
  # instance_initiated_shutdown_behavior - (optional) is a type of string
  instance_initiated_shutdown_behavior = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # kernel_id - (optional) is a type of string
  kernel_id = null
  # key_name - (optional) is a type of string
  key_name = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # ram_disk_id - (optional) is a type of string
  ram_disk_id = null
  # security_group_names - (optional) is a type of set of string
  security_group_names = []
  # tags - (optional) is a type of map of string
  tags = {}
  # update_default_version - (optional) is a type of bool
  update_default_version = null
  # user_data - (optional) is a type of string
  user_data = null
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

  block_device_mappings = [{
    device_name = null
    ebs = [{
      delete_on_termination = null
      encrypted             = null
      iops                  = null
      kms_key_id            = null
      snapshot_id           = null
      throughput            = null
      volume_size           = null
      volume_type           = null
    }]
    no_device    = null
    virtual_name = null
  }]

  capacity_reservation_specification = [{
    capacity_reservation_preference = null
    capacity_reservation_target = [{
      capacity_reservation_id = null
    }]
  }]

  cpu_options = [{
    core_count       = null
    threads_per_core = null
  }]

  credit_specification = [{
    cpu_credits = null
  }]

  elastic_gpu_specifications = [{
    type = null
  }]

  elastic_inference_accelerator = [{
    type = null
  }]

  enclave_options = [{
    enabled = null
  }]

  hibernation_options = [{
    configured = null
  }]

  iam_instance_profile = [{
    arn  = null
    name = null
  }]

  instance_market_options = [{
    market_type = null
    spot_options = [{
      block_duration_minutes         = null
      instance_interruption_behavior = null
      max_price                      = null
      spot_instance_type             = null
      valid_until                    = null
    }]
  }]

  license_specification = [{
    license_configuration_arn = null
  }]

  metadata_options = [{
    http_endpoint               = null
    http_put_response_hop_limit = null
    http_tokens                 = null
  }]

  monitoring = [{
    enabled = null
  }]

  network_interfaces = [{
    associate_carrier_ip_address = null
    associate_public_ip_address  = null
    delete_on_termination        = null
    description                  = null
    device_index                 = null
    ipv4_address_count           = null
    ipv4_addresses               = []
    ipv6_address_count           = null
    ipv6_addresses               = []
    network_interface_id         = null
    private_ip_address           = null
    security_groups              = []
    subnet_id                    = null
  }]

  placement = [{
    affinity          = null
    availability_zone = null
    group_name        = null
    host_id           = null
    partition_number  = null
    spread_domain     = null
    tenancy           = null
  }]

  tag_specifications = [{
    resource_type = null
    tags          = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_api_termination" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_initiated_shutdown_behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kernel_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ram_disk_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "update_default_version" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "block_device_mappings" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      device_name = string
      ebs = list(object(
        {
          delete_on_termination = string
          encrypted             = string
          iops                  = number
          kms_key_id            = string
          snapshot_id           = string
          throughput            = number
          volume_size           = number
          volume_type           = string
        }
      ))
      no_device    = string
      virtual_name = string
    }
  ))
  default = []
}

variable "capacity_reservation_specification" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      capacity_reservation_preference = string
      capacity_reservation_target = list(object(
        {
          capacity_reservation_id = string
        }
      ))
    }
  ))
  default = []
}

variable "cpu_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      core_count       = number
      threads_per_core = number
    }
  ))
  default = []
}

variable "credit_specification" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cpu_credits = string
    }
  ))
  default = []
}

variable "elastic_gpu_specifications" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "elastic_inference_accelerator" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "enclave_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "hibernation_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      configured = bool
    }
  ))
  default = []
}

variable "iam_instance_profile" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arn  = string
      name = string
    }
  ))
  default = []
}

variable "instance_market_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      market_type = string
      spot_options = list(object(
        {
          block_duration_minutes         = number
          instance_interruption_behavior = string
          max_price                      = string
          spot_instance_type             = string
          valid_until                    = string
        }
      ))
    }
  ))
  default = []
}

variable "license_specification" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      license_configuration_arn = string
    }
  ))
  default = []
}

variable "metadata_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http_endpoint               = string
      http_put_response_hop_limit = number
      http_tokens                 = string
    }
  ))
  default = []
}

variable "monitoring" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "network_interfaces" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      associate_carrier_ip_address = string
      associate_public_ip_address  = string
      delete_on_termination        = string
      description                  = string
      device_index                 = number
      ipv4_address_count           = number
      ipv4_addresses               = set(string)
      ipv6_address_count           = number
      ipv6_addresses               = set(string)
      network_interface_id         = string
      private_ip_address           = string
      security_groups              = set(string)
      subnet_id                    = string
    }
  ))
  default = []
}

variable "placement" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      affinity          = string
      availability_zone = string
      group_name        = string
      host_id           = string
      partition_number  = number
      spread_domain     = string
      tenancy           = string
    }
  ))
  default = []
}

variable "tag_specifications" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      resource_type = string
      tags          = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_launch_template" "this" {
  default_version                      = var.default_version
  description                          = var.description
  disable_api_termination              = var.disable_api_termination
  ebs_optimized                        = var.ebs_optimized
  image_id                             = var.image_id
  instance_initiated_shutdown_behavior = var.instance_initiated_shutdown_behavior
  instance_type                        = var.instance_type
  kernel_id                            = var.kernel_id
  key_name                             = var.key_name
  name                                 = var.name
  name_prefix                          = var.name_prefix
  ram_disk_id                          = var.ram_disk_id
  security_group_names                 = var.security_group_names
  tags                                 = var.tags
  update_default_version               = var.update_default_version
  user_data                            = var.user_data
  vpc_security_group_ids               = var.vpc_security_group_ids

  dynamic "block_device_mappings" {
    for_each = var.block_device_mappings
    content {
      device_name  = block_device_mappings.value["device_name"]
      no_device    = block_device_mappings.value["no_device"]
      virtual_name = block_device_mappings.value["virtual_name"]

      dynamic "ebs" {
        for_each = block_device_mappings.value.ebs
        content {
          delete_on_termination = ebs.value["delete_on_termination"]
          encrypted             = ebs.value["encrypted"]
          iops                  = ebs.value["iops"]
          kms_key_id            = ebs.value["kms_key_id"]
          snapshot_id           = ebs.value["snapshot_id"]
          throughput            = ebs.value["throughput"]
          volume_size           = ebs.value["volume_size"]
          volume_type           = ebs.value["volume_type"]
        }
      }

    }
  }

  dynamic "capacity_reservation_specification" {
    for_each = var.capacity_reservation_specification
    content {
      capacity_reservation_preference = capacity_reservation_specification.value["capacity_reservation_preference"]

      dynamic "capacity_reservation_target" {
        for_each = capacity_reservation_specification.value.capacity_reservation_target
        content {
          capacity_reservation_id = capacity_reservation_target.value["capacity_reservation_id"]
        }
      }

    }
  }

  dynamic "cpu_options" {
    for_each = var.cpu_options
    content {
      core_count       = cpu_options.value["core_count"]
      threads_per_core = cpu_options.value["threads_per_core"]
    }
  }

  dynamic "credit_specification" {
    for_each = var.credit_specification
    content {
      cpu_credits = credit_specification.value["cpu_credits"]
    }
  }

  dynamic "elastic_gpu_specifications" {
    for_each = var.elastic_gpu_specifications
    content {
      type = elastic_gpu_specifications.value["type"]
    }
  }

  dynamic "elastic_inference_accelerator" {
    for_each = var.elastic_inference_accelerator
    content {
      type = elastic_inference_accelerator.value["type"]
    }
  }

  dynamic "enclave_options" {
    for_each = var.enclave_options
    content {
      enabled = enclave_options.value["enabled"]
    }
  }

  dynamic "hibernation_options" {
    for_each = var.hibernation_options
    content {
      configured = hibernation_options.value["configured"]
    }
  }

  dynamic "iam_instance_profile" {
    for_each = var.iam_instance_profile
    content {
      arn  = iam_instance_profile.value["arn"]
      name = iam_instance_profile.value["name"]
    }
  }

  dynamic "instance_market_options" {
    for_each = var.instance_market_options
    content {
      market_type = instance_market_options.value["market_type"]

      dynamic "spot_options" {
        for_each = instance_market_options.value.spot_options
        content {
          block_duration_minutes         = spot_options.value["block_duration_minutes"]
          instance_interruption_behavior = spot_options.value["instance_interruption_behavior"]
          max_price                      = spot_options.value["max_price"]
          spot_instance_type             = spot_options.value["spot_instance_type"]
          valid_until                    = spot_options.value["valid_until"]
        }
      }

    }
  }

  dynamic "license_specification" {
    for_each = var.license_specification
    content {
      license_configuration_arn = license_specification.value["license_configuration_arn"]
    }
  }

  dynamic "metadata_options" {
    for_each = var.metadata_options
    content {
      http_endpoint               = metadata_options.value["http_endpoint"]
      http_put_response_hop_limit = metadata_options.value["http_put_response_hop_limit"]
      http_tokens                 = metadata_options.value["http_tokens"]
    }
  }

  dynamic "monitoring" {
    for_each = var.monitoring
    content {
      enabled = monitoring.value["enabled"]
    }
  }

  dynamic "network_interfaces" {
    for_each = var.network_interfaces
    content {
      associate_carrier_ip_address = network_interfaces.value["associate_carrier_ip_address"]
      associate_public_ip_address  = network_interfaces.value["associate_public_ip_address"]
      delete_on_termination        = network_interfaces.value["delete_on_termination"]
      description                  = network_interfaces.value["description"]
      device_index                 = network_interfaces.value["device_index"]
      ipv4_address_count           = network_interfaces.value["ipv4_address_count"]
      ipv4_addresses               = network_interfaces.value["ipv4_addresses"]
      ipv6_address_count           = network_interfaces.value["ipv6_address_count"]
      ipv6_addresses               = network_interfaces.value["ipv6_addresses"]
      network_interface_id         = network_interfaces.value["network_interface_id"]
      private_ip_address           = network_interfaces.value["private_ip_address"]
      security_groups              = network_interfaces.value["security_groups"]
      subnet_id                    = network_interfaces.value["subnet_id"]
    }
  }

  dynamic "placement" {
    for_each = var.placement
    content {
      affinity          = placement.value["affinity"]
      availability_zone = placement.value["availability_zone"]
      group_name        = placement.value["group_name"]
      host_id           = placement.value["host_id"]
      partition_number  = placement.value["partition_number"]
      spread_domain     = placement.value["spread_domain"]
      tenancy           = placement.value["tenancy"]
    }
  }

  dynamic "tag_specifications" {
    for_each = var.tag_specifications
    content {
      resource_type = tag_specifications.value["resource_type"]
      tags          = tag_specifications.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_launch_template.this.arn
}

output "default_version" {
  description = "returns a number"
  value       = aws_launch_template.this.default_version
}

output "id" {
  description = "returns a string"
  value       = aws_launch_template.this.id
}

output "latest_version" {
  description = "returns a number"
  value       = aws_launch_template.this.latest_version
}

output "name" {
  description = "returns a string"
  value       = aws_launch_template.this.name
}

output "this" {
  value = aws_launch_template.this
}
```

[top](#index)