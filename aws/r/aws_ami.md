# aws_ami

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
module "aws_ami" {
  source = "./modules/aws/r/aws_ami"

  # architecture - (optional) is a type of string
  architecture = null
  # description - (optional) is a type of string
  description = null
  # ena_support - (optional) is a type of bool
  ena_support = null
  # image_location - (optional) is a type of string
  image_location = null
  # kernel_id - (optional) is a type of string
  kernel_id = null
  # name - (required) is a type of string
  name = null
  # ramdisk_id - (optional) is a type of string
  ramdisk_id = null
  # root_device_name - (optional) is a type of string
  root_device_name = null
  # sriov_net_support - (optional) is a type of string
  sriov_net_support = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtualization_type - (optional) is a type of string
  virtualization_type = null

  ebs_block_device = [{
    delete_on_termination = null
    device_name           = null
    encrypted             = null
    iops                  = null
    snapshot_id           = null
    throughput            = null
    volume_size           = null
    volume_type           = null
  }]

  ephemeral_block_device = [{
    device_name  = null
    virtual_name = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "architecture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ena_support" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "image_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kernel_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ramdisk_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "root_device_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sriov_net_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtualization_type" {
  description = "(optional)"
  type        = string
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
      snapshot_id           = string
      throughput            = number
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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ami" "this" {
  architecture        = var.architecture
  description         = var.description
  ena_support         = var.ena_support
  image_location      = var.image_location
  kernel_id           = var.kernel_id
  name                = var.name
  ramdisk_id          = var.ramdisk_id
  root_device_name    = var.root_device_name
  sriov_net_support   = var.sriov_net_support
  tags                = var.tags
  virtualization_type = var.virtualization_type

  dynamic "ebs_block_device" {
    for_each = var.ebs_block_device
    content {
      delete_on_termination = ebs_block_device.value["delete_on_termination"]
      device_name           = ebs_block_device.value["device_name"]
      encrypted             = ebs_block_device.value["encrypted"]
      iops                  = ebs_block_device.value["iops"]
      snapshot_id           = ebs_block_device.value["snapshot_id"]
      throughput            = ebs_block_device.value["throughput"]
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

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ami.this.arn
}

output "hypervisor" {
  description = "returns a string"
  value       = aws_ami.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = aws_ami.this.id
}

output "image_location" {
  description = "returns a string"
  value       = aws_ami.this.image_location
}

output "image_owner_alias" {
  description = "returns a string"
  value       = aws_ami.this.image_owner_alias
}

output "image_type" {
  description = "returns a string"
  value       = aws_ami.this.image_type
}

output "manage_ebs_snapshots" {
  description = "returns a bool"
  value       = aws_ami.this.manage_ebs_snapshots
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ami.this.owner_id
}

output "platform" {
  description = "returns a string"
  value       = aws_ami.this.platform
}

output "platform_details" {
  description = "returns a string"
  value       = aws_ami.this.platform_details
}

output "public" {
  description = "returns a bool"
  value       = aws_ami.this.public
}

output "root_snapshot_id" {
  description = "returns a string"
  value       = aws_ami.this.root_snapshot_id
}

output "usage_operation" {
  description = "returns a string"
  value       = aws_ami.this.usage_operation
}

output "this" {
  value = aws_ami.this
}
```

[top](#index)