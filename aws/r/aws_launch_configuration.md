# aws_launch_configuration

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
module "aws_launch_configuration" {
  source = "./modules/aws/r/aws_launch_configuration"

  # associate_public_ip_address - (optional) is a type of bool
  associate_public_ip_address = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # enable_monitoring - (optional) is a type of bool
  enable_monitoring = null
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # image_id - (required) is a type of string
  image_id = null
  # instance_type - (required) is a type of string
  instance_type = null
  # key_name - (optional) is a type of string
  key_name = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # placement_tenancy - (optional) is a type of string
  placement_tenancy = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # spot_price - (optional) is a type of string
  spot_price = null
  # user_data - (optional) is a type of string
  user_data = null
  # user_data_base64 - (optional) is a type of string
  user_data_base64 = null
  # vpc_classic_link_id - (optional) is a type of string
  vpc_classic_link_id = null
  # vpc_classic_link_security_groups - (optional) is a type of set of string
  vpc_classic_link_security_groups = []

  ebs_block_device = [{
    delete_on_termination = null
    device_name           = null
    encrypted             = null
    iops                  = null
    no_device             = null
    snapshot_id           = null
    volume_size           = null
    volume_type           = null
  }]

  ephemeral_block_device = [{
    device_name  = null
    virtual_name = null
  }]

  metadata_options = [{
    http_endpoint               = null
    http_put_response_hop_limit = null
    http_tokens                 = null
  }]

  root_block_device = [{
    delete_on_termination = null
    encrypted             = null
    iops                  = null
    volume_size           = null
    volume_type           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "associate_public_ip_address" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_monitoring" {
  description = "(optional)"
  type        = bool
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

variable "instance_type" {
  description = "(required)"
  type        = string
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

variable "placement_tenancy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "spot_price" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data_base64" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_classic_link_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_classic_link_security_groups" {
  description = "(optional)"
  type        = set(string)
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
      no_device             = bool
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

variable "metadata_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http_endpoint               = string
      http_put_response_hop_limit = number
      http_tokens                 = string
    }
  ))
  default = []
}

variable "root_block_device" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_on_termination = bool
      encrypted             = bool
      iops                  = number
      volume_size           = number
      volume_type           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_launch_configuration" "this" {
  associate_public_ip_address      = var.associate_public_ip_address
  ebs_optimized                    = var.ebs_optimized
  enable_monitoring                = var.enable_monitoring
  iam_instance_profile             = var.iam_instance_profile
  image_id                         = var.image_id
  instance_type                    = var.instance_type
  key_name                         = var.key_name
  name                             = var.name
  name_prefix                      = var.name_prefix
  placement_tenancy                = var.placement_tenancy
  security_groups                  = var.security_groups
  spot_price                       = var.spot_price
  user_data                        = var.user_data
  user_data_base64                 = var.user_data_base64
  vpc_classic_link_id              = var.vpc_classic_link_id
  vpc_classic_link_security_groups = var.vpc_classic_link_security_groups

  dynamic "ebs_block_device" {
    for_each = var.ebs_block_device
    content {
      delete_on_termination = ebs_block_device.value["delete_on_termination"]
      device_name           = ebs_block_device.value["device_name"]
      encrypted             = ebs_block_device.value["encrypted"]
      iops                  = ebs_block_device.value["iops"]
      no_device             = ebs_block_device.value["no_device"]
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

  dynamic "metadata_options" {
    for_each = var.metadata_options
    content {
      http_endpoint               = metadata_options.value["http_endpoint"]
      http_put_response_hop_limit = metadata_options.value["http_put_response_hop_limit"]
      http_tokens                 = metadata_options.value["http_tokens"]
    }
  }

  dynamic "root_block_device" {
    for_each = var.root_block_device
    content {
      delete_on_termination = root_block_device.value["delete_on_termination"]
      encrypted             = root_block_device.value["encrypted"]
      iops                  = root_block_device.value["iops"]
      volume_size           = root_block_device.value["volume_size"]
      volume_type           = root_block_device.value["volume_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_launch_configuration.this.arn
}

output "ebs_optimized" {
  description = "returns a bool"
  value       = aws_launch_configuration.this.ebs_optimized
}

output "id" {
  description = "returns a string"
  value       = aws_launch_configuration.this.id
}

output "key_name" {
  description = "returns a string"
  value       = aws_launch_configuration.this.key_name
}

output "name" {
  description = "returns a string"
  value       = aws_launch_configuration.this.name
}

output "this" {
  value = aws_launch_configuration.this
}
```

[top](#index)