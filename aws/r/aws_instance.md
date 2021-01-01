# aws_instance

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_instance" {
  source = "./modules/aws/r/aws_instance"

  # ami - (required) is a type of string
  ami = null
  # associate_public_ip_address - (optional) is a type of bool
  associate_public_ip_address = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cpu_core_count - (optional) is a type of number
  cpu_core_count = null
  # cpu_threads_per_core - (optional) is a type of number
  cpu_threads_per_core = null
  # disable_api_termination - (optional) is a type of bool
  disable_api_termination = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # get_password_data - (optional) is a type of bool
  get_password_data = null
  # hibernation - (optional) is a type of bool
  hibernation = null
  # host_id - (optional) is a type of string
  host_id = null
  # iam_instance_profile - (optional) is a type of string
  iam_instance_profile = null
  # instance_initiated_shutdown_behavior - (optional) is a type of string
  instance_initiated_shutdown_behavior = null
  # instance_type - (required) is a type of string
  instance_type = null
  # ipv6_address_count - (optional) is a type of number
  ipv6_address_count = null
  # ipv6_addresses - (optional) is a type of list of string
  ipv6_addresses = []
  # key_name - (optional) is a type of string
  key_name = null
  # monitoring - (optional) is a type of bool
  monitoring = null
  # placement_group - (optional) is a type of string
  placement_group = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # secondary_private_ips - (optional) is a type of set of string
  secondary_private_ips = []
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # source_dest_check - (optional) is a type of bool
  source_dest_check = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenancy - (optional) is a type of string
  tenancy = null
  # user_data - (optional) is a type of string
  user_data = null
  # user_data_base64 - (optional) is a type of string
  user_data_base64 = null
  # volume_tags - (optional) is a type of map of string
  volume_tags = {}
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

  credit_specification = [{
    cpu_credits = null
  }]

  ebs_block_device = [{
    delete_on_termination = null
    device_name           = null
    encrypted             = null
    iops                  = null
    kms_key_id            = null
    snapshot_id           = null
    throughput            = null
    volume_id             = null
    volume_size           = null
    volume_type           = null
  }]

  enclave_options = [{
    enabled = null
  }]

  ephemeral_block_device = [{
    device_name  = null
    no_device    = null
    virtual_name = null
  }]

  metadata_options = [{
    http_endpoint               = null
    http_put_response_hop_limit = null
    http_tokens                 = null
  }]

  network_interface = [{
    delete_on_termination = null
    device_index          = null
    network_interface_id  = null
  }]

  root_block_device = [{
    delete_on_termination = null
    device_name           = null
    encrypted             = null
    iops                  = null
    kms_key_id            = null
    throughput            = null
    volume_id             = null
    volume_size           = null
    volume_type           = null
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

```hcl
variable "ami" {
  description = "(required)"
  type        = string
}

variable "associate_public_ip_address" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_core_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cpu_threads_per_core" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_api_termination" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "get_password_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hibernation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "host_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_instance_profile" {
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
  description = "(required)"
  type        = string
}

variable "ipv6_address_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_addresses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "placement_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_private_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_dest_check" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tenancy" {
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

variable "volume_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
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

variable "ebs_block_device" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      delete_on_termination = bool
      device_name           = string
      encrypted             = bool
      iops                  = number
      kms_key_id            = string
      snapshot_id           = string
      throughput            = number
      volume_id             = string
      volume_size           = number
      volume_type           = string
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

variable "ephemeral_block_device" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      device_name  = string
      no_device    = bool
      virtual_name = string
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

variable "network_interface" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      delete_on_termination = bool
      device_index          = number
      network_interface_id  = string
    }
  ))
  default = []
}

variable "root_block_device" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_on_termination = bool
      device_name           = string
      encrypted             = bool
      iops                  = number
      kms_key_id            = string
      throughput            = number
      volume_id             = string
      volume_size           = number
      volume_type           = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "aws_instance" "this" {
  ami                                  = var.ami
  associate_public_ip_address          = var.associate_public_ip_address
  availability_zone                    = var.availability_zone
  cpu_core_count                       = var.cpu_core_count
  cpu_threads_per_core                 = var.cpu_threads_per_core
  disable_api_termination              = var.disable_api_termination
  ebs_optimized                        = var.ebs_optimized
  get_password_data                    = var.get_password_data
  hibernation                          = var.hibernation
  host_id                              = var.host_id
  iam_instance_profile                 = var.iam_instance_profile
  instance_initiated_shutdown_behavior = var.instance_initiated_shutdown_behavior
  instance_type                        = var.instance_type
  ipv6_address_count                   = var.ipv6_address_count
  ipv6_addresses                       = var.ipv6_addresses
  key_name                             = var.key_name
  monitoring                           = var.monitoring
  placement_group                      = var.placement_group
  private_ip                           = var.private_ip
  secondary_private_ips                = var.secondary_private_ips
  security_groups                      = var.security_groups
  source_dest_check                    = var.source_dest_check
  subnet_id                            = var.subnet_id
  tags                                 = var.tags
  tenancy                              = var.tenancy
  user_data                            = var.user_data
  user_data_base64                     = var.user_data_base64
  volume_tags                          = var.volume_tags
  vpc_security_group_ids               = var.vpc_security_group_ids

  dynamic "credit_specification" {
    for_each = var.credit_specification
    content {
      cpu_credits = credit_specification.value["cpu_credits"]
    }
  }

  dynamic "ebs_block_device" {
    for_each = var.ebs_block_device
    content {
      delete_on_termination = ebs_block_device.value["delete_on_termination"]
      device_name           = ebs_block_device.value["device_name"]
      encrypted             = ebs_block_device.value["encrypted"]
      iops                  = ebs_block_device.value["iops"]
      kms_key_id            = ebs_block_device.value["kms_key_id"]
      snapshot_id           = ebs_block_device.value["snapshot_id"]
      throughput            = ebs_block_device.value["throughput"]
      volume_size           = ebs_block_device.value["volume_size"]
      volume_type           = ebs_block_device.value["volume_type"]
    }
  }

  dynamic "enclave_options" {
    for_each = var.enclave_options
    content {
      enabled = enclave_options.value["enabled"]
    }
  }

  dynamic "ephemeral_block_device" {
    for_each = var.ephemeral_block_device
    content {
      device_name  = ephemeral_block_device.value["device_name"]
      no_device    = ephemeral_block_device.value["no_device"]
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

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      delete_on_termination = network_interface.value["delete_on_termination"]
      device_index          = network_interface.value["device_index"]
      network_interface_id  = network_interface.value["network_interface_id"]
    }
  }

  dynamic "root_block_device" {
    for_each = var.root_block_device
    content {
      delete_on_termination = root_block_device.value["delete_on_termination"]
      encrypted             = root_block_device.value["encrypted"]
      iops                  = root_block_device.value["iops"]
      kms_key_id            = root_block_device.value["kms_key_id"]
      throughput            = root_block_device.value["throughput"]
      volume_size           = root_block_device.value["volume_size"]
      volume_type           = root_block_device.value["volume_type"]
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

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_instance.this.arn
}

output "associate_public_ip_address" {
  description = "returns a bool"
  value       = aws_instance.this.associate_public_ip_address
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_instance.this.availability_zone
}

output "cpu_core_count" {
  description = "returns a number"
  value       = aws_instance.this.cpu_core_count
}

output "cpu_threads_per_core" {
  description = "returns a number"
  value       = aws_instance.this.cpu_threads_per_core
}

output "host_id" {
  description = "returns a string"
  value       = aws_instance.this.host_id
}

output "id" {
  description = "returns a string"
  value       = aws_instance.this.id
}

output "instance_state" {
  description = "returns a string"
  value       = aws_instance.this.instance_state
}

output "ipv6_address_count" {
  description = "returns a number"
  value       = aws_instance.this.ipv6_address_count
}

output "ipv6_addresses" {
  description = "returns a list of string"
  value       = aws_instance.this.ipv6_addresses
}

output "key_name" {
  description = "returns a string"
  value       = aws_instance.this.key_name
}

output "outpost_arn" {
  description = "returns a string"
  value       = aws_instance.this.outpost_arn
}

output "password_data" {
  description = "returns a string"
  value       = aws_instance.this.password_data
}

output "placement_group" {
  description = "returns a string"
  value       = aws_instance.this.placement_group
}

output "primary_network_interface_id" {
  description = "returns a string"
  value       = aws_instance.this.primary_network_interface_id
}

output "private_dns" {
  description = "returns a string"
  value       = aws_instance.this.private_dns
}

output "private_ip" {
  description = "returns a string"
  value       = aws_instance.this.private_ip
}

output "public_dns" {
  description = "returns a string"
  value       = aws_instance.this.public_dns
}

output "public_ip" {
  description = "returns a string"
  value       = aws_instance.this.public_ip
}

output "secondary_private_ips" {
  description = "returns a set of string"
  value       = aws_instance.this.secondary_private_ips
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_instance.this.security_groups
}

output "subnet_id" {
  description = "returns a string"
  value       = aws_instance.this.subnet_id
}

output "tenancy" {
  description = "returns a string"
  value       = aws_instance.this.tenancy
}

output "volume_tags" {
  description = "returns a map of string"
  value       = aws_instance.this.volume_tags
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_instance.this.vpc_security_group_ids
}

output "this" {
  value = aws_instance.this
}
```

[top](#index)