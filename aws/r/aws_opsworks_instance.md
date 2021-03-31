# aws_opsworks_instance

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
module "aws_opsworks_instance" {
  source = "./modules/aws/r/aws_opsworks_instance"

  # agent_version - (optional) is a type of string
  agent_version = null
  # ami_id - (optional) is a type of string
  ami_id = null
  # architecture - (optional) is a type of string
  architecture = null
  # auto_scaling_type - (optional) is a type of string
  auto_scaling_type = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # created_at - (optional) is a type of string
  created_at = null
  # delete_ebs - (optional) is a type of bool
  delete_ebs = null
  # delete_eip - (optional) is a type of bool
  delete_eip = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # ecs_cluster_arn - (optional) is a type of string
  ecs_cluster_arn = null
  # elastic_ip - (optional) is a type of string
  elastic_ip = null
  # hostname - (optional) is a type of string
  hostname = null
  # infrastructure_class - (optional) is a type of string
  infrastructure_class = null
  # install_updates_on_boot - (optional) is a type of bool
  install_updates_on_boot = null
  # instance_profile_arn - (optional) is a type of string
  instance_profile_arn = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # last_service_error_id - (optional) is a type of string
  last_service_error_id = null
  # layer_ids - (required) is a type of list of string
  layer_ids = []
  # os - (optional) is a type of string
  os = null
  # platform - (optional) is a type of string
  platform = null
  # private_dns - (optional) is a type of string
  private_dns = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # public_dns - (optional) is a type of string
  public_dns = null
  # public_ip - (optional) is a type of string
  public_ip = null
  # registered_by - (optional) is a type of string
  registered_by = null
  # reported_agent_version - (optional) is a type of string
  reported_agent_version = null
  # reported_os_family - (optional) is a type of string
  reported_os_family = null
  # reported_os_name - (optional) is a type of string
  reported_os_name = null
  # reported_os_version - (optional) is a type of string
  reported_os_version = null
  # root_device_type - (optional) is a type of string
  root_device_type = null
  # root_device_volume_id - (optional) is a type of string
  root_device_volume_id = null
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = []
  # ssh_host_dsa_key_fingerprint - (optional) is a type of string
  ssh_host_dsa_key_fingerprint = null
  # ssh_host_rsa_key_fingerprint - (optional) is a type of string
  ssh_host_rsa_key_fingerprint = null
  # ssh_key_name - (optional) is a type of string
  ssh_key_name = null
  # stack_id - (required) is a type of string
  stack_id = null
  # state - (optional) is a type of string
  state = null
  # status - (optional) is a type of string
  status = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tenancy - (optional) is a type of string
  tenancy = null
  # virtualization_type - (optional) is a type of string
  virtualization_type = null

  ebs_block_device = [{
    delete_on_termination = null
    device_name           = null
    iops                  = null
    snapshot_id           = null
    volume_size           = null
    volume_type           = null
  }]

  ephemeral_block_device = [{
    device_name  = null
    virtual_name = null
  }]

  root_block_device = [{
    delete_on_termination = null
    iops                  = null
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

```terraform
variable "agent_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ami_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "architecture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_scaling_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_ebs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "delete_eip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ecs_cluster_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elastic_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "infrastructure_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "install_updates_on_boot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_profile_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_service_error_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "layer_ids" {
  description = "(required)"
  type        = list(string)
}

variable "os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "registered_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reported_agent_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reported_os_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reported_os_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reported_os_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "root_device_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "root_device_volume_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ssh_host_dsa_key_fingerprint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_host_rsa_key_fingerprint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_id" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenancy" {
  description = "(optional)"
  type        = string
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
      iops                  = number
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

variable "root_block_device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      delete_on_termination = bool
      iops                  = number
      volume_size           = number
      volume_type           = string
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
resource "aws_opsworks_instance" "this" {
  agent_version                = var.agent_version
  ami_id                       = var.ami_id
  architecture                 = var.architecture
  auto_scaling_type            = var.auto_scaling_type
  availability_zone            = var.availability_zone
  created_at                   = var.created_at
  delete_ebs                   = var.delete_ebs
  delete_eip                   = var.delete_eip
  ebs_optimized                = var.ebs_optimized
  ecs_cluster_arn              = var.ecs_cluster_arn
  elastic_ip                   = var.elastic_ip
  hostname                     = var.hostname
  infrastructure_class         = var.infrastructure_class
  install_updates_on_boot      = var.install_updates_on_boot
  instance_profile_arn         = var.instance_profile_arn
  instance_type                = var.instance_type
  last_service_error_id        = var.last_service_error_id
  layer_ids                    = var.layer_ids
  os                           = var.os
  platform                     = var.platform
  private_dns                  = var.private_dns
  private_ip                   = var.private_ip
  public_dns                   = var.public_dns
  public_ip                    = var.public_ip
  registered_by                = var.registered_by
  reported_agent_version       = var.reported_agent_version
  reported_os_family           = var.reported_os_family
  reported_os_name             = var.reported_os_name
  reported_os_version          = var.reported_os_version
  root_device_type             = var.root_device_type
  root_device_volume_id        = var.root_device_volume_id
  security_group_ids           = var.security_group_ids
  ssh_host_dsa_key_fingerprint = var.ssh_host_dsa_key_fingerprint
  ssh_host_rsa_key_fingerprint = var.ssh_host_rsa_key_fingerprint
  ssh_key_name                 = var.ssh_key_name
  stack_id                     = var.stack_id
  state                        = var.state
  status                       = var.status
  subnet_id                    = var.subnet_id
  tenancy                      = var.tenancy
  virtualization_type          = var.virtualization_type

  dynamic "ebs_block_device" {
    for_each = var.ebs_block_device
    content {
      delete_on_termination = ebs_block_device.value["delete_on_termination"]
      device_name           = ebs_block_device.value["device_name"]
      iops                  = ebs_block_device.value["iops"]
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

  dynamic "root_block_device" {
    for_each = var.root_block_device
    content {
      delete_on_termination = root_block_device.value["delete_on_termination"]
      iops                  = root_block_device.value["iops"]
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

```terraform
output "ami_id" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.ami_id
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.availability_zone
}

output "created_at" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.created_at
}

output "ec2_instance_id" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.ec2_instance_id
}

output "ecs_cluster_arn" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.ecs_cluster_arn
}

output "elastic_ip" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.elastic_ip
}

output "hostname" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.hostname
}

output "id" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.id
}

output "infrastructure_class" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.infrastructure_class
}

output "instance_profile_arn" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.instance_profile_arn
}

output "last_service_error_id" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.last_service_error_id
}

output "os" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.os
}

output "platform" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.platform
}

output "private_dns" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.private_dns
}

output "private_ip" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.private_ip
}

output "public_dns" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.public_dns
}

output "public_ip" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.public_ip
}

output "registered_by" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.registered_by
}

output "reported_agent_version" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.reported_agent_version
}

output "reported_os_family" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.reported_os_family
}

output "reported_os_name" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.reported_os_name
}

output "reported_os_version" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.reported_os_version
}

output "root_device_type" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.root_device_type
}

output "root_device_volume_id" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.root_device_volume_id
}

output "security_group_ids" {
  description = "returns a list of string"
  value       = aws_opsworks_instance.this.security_group_ids
}

output "ssh_host_dsa_key_fingerprint" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.ssh_host_dsa_key_fingerprint
}

output "ssh_host_rsa_key_fingerprint" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.ssh_host_rsa_key_fingerprint
}

output "ssh_key_name" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.ssh_key_name
}

output "status" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.status
}

output "subnet_id" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.subnet_id
}

output "tenancy" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.tenancy
}

output "virtualization_type" {
  description = "returns a string"
  value       = aws_opsworks_instance.this.virtualization_type
}

output "this" {
  value = aws_opsworks_instance.this
}
```

[top](#index)