# aws_ec2_instance_type

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ec2_instance_type" {
  source = "./modules/aws/d/aws_ec2_instance_type"

  # default_cores - (optional) is a type of number
  default_cores = null
  # default_threads_per_core - (optional) is a type of number
  default_threads_per_core = null
  # hypervisor - (optional) is a type of string
  hypervisor = null
  # instance_type - (required) is a type of string
  instance_type = null
  # maximum_ipv6_addresses_per_interface - (optional) is a type of number
  maximum_ipv6_addresses_per_interface = null
  # total_fpga_memory - (optional) is a type of number
  total_fpga_memory = null
  # total_gpu_memory - (optional) is a type of number
  total_gpu_memory = null
  # total_instance_storage - (optional) is a type of number
  total_instance_storage = null

  fpgas = [{
    count        = null
    manufacturer = null
    memory_size  = null
    name         = null
  }]

  gpus = [{
    count        = null
    manufacturer = null
    memory_size  = null
    name         = null
  }]

  inference_accelerators = [{
    count        = null
    manufacturer = null
    name         = null
  }]

  instance_disks = [{
    count = null
    size  = null
    type  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_cores" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_threads_per_core" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hypervisor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "maximum_ipv6_addresses_per_interface" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "total_fpga_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "total_gpu_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "total_instance_storage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fpgas" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      count        = number
      manufacturer = string
      memory_size  = number
      name         = string
    }
  ))
  default = []
}

variable "gpus" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      count        = number
      manufacturer = string
      memory_size  = number
      name         = string
    }
  ))
  default = []
}

variable "inference_accelerators" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      count        = number
      manufacturer = string
      name         = string
    }
  ))
  default = []
}

variable "instance_disks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      count = number
      size  = number
      type  = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_ec2_instance_type" "this" {
  default_cores                        = var.default_cores
  default_threads_per_core             = var.default_threads_per_core
  hypervisor                           = var.hypervisor
  instance_type                        = var.instance_type
  maximum_ipv6_addresses_per_interface = var.maximum_ipv6_addresses_per_interface
  total_fpga_memory                    = var.total_fpga_memory
  total_gpu_memory                     = var.total_gpu_memory
  total_instance_storage               = var.total_instance_storage

  dynamic "fpgas" {
    for_each = var.fpgas
    content {
    }
  }

  dynamic "gpus" {
    for_each = var.gpus
    content {
    }
  }

  dynamic "inference_accelerators" {
    for_each = var.inference_accelerators
    content {
    }
  }

  dynamic "instance_disks" {
    for_each = var.instance_disks
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_recovery_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.auto_recovery_supported
}

output "bare_metal" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.bare_metal
}

output "burstable_performance_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.burstable_performance_supported
}

output "current_generation" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.current_generation
}

output "dedicated_hosts_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.dedicated_hosts_supported
}

output "default_cores" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.default_cores
}

output "default_threads_per_core" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.default_threads_per_core
}

output "default_vcpus" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.default_vcpus
}

output "ebs_encryption_support" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.ebs_encryption_support
}

output "ebs_nvme_support" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.ebs_nvme_support
}

output "ebs_optimized_support" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.ebs_optimized_support
}

output "ebs_performance_baseline_bandwidth" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.ebs_performance_baseline_bandwidth
}

output "ebs_performance_baseline_iops" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.ebs_performance_baseline_iops
}

output "ebs_performance_baseline_throughput" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.ebs_performance_baseline_throughput
}

output "ebs_performance_maximum_bandwidth" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.ebs_performance_maximum_bandwidth
}

output "ebs_performance_maximum_iops" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.ebs_performance_maximum_iops
}

output "ebs_performance_maximum_throughput" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.ebs_performance_maximum_throughput
}

output "efa_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.efa_supported
}

output "ena_support" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.ena_support
}

output "free_tier_eligible" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.free_tier_eligible
}

output "hibernation_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.hibernation_supported
}

output "hypervisor" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.id
}

output "instance_storage_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.instance_storage_supported
}

output "ipv6_supported" {
  description = "returns a bool"
  value       = data.aws_ec2_instance_type.this.ipv6_supported
}

output "maximum_ipv4_addresses_per_interface" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.maximum_ipv4_addresses_per_interface
}

output "maximum_ipv6_addresses_per_interface" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.maximum_ipv6_addresses_per_interface
}

output "maximum_network_interfaces" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.maximum_network_interfaces
}

output "memory_size" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.memory_size
}

output "network_performance" {
  description = "returns a string"
  value       = data.aws_ec2_instance_type.this.network_performance
}

output "supported_architectures" {
  description = "returns a list of string"
  value       = data.aws_ec2_instance_type.this.supported_architectures
}

output "supported_placement_strategies" {
  description = "returns a list of string"
  value       = data.aws_ec2_instance_type.this.supported_placement_strategies
}

output "supported_root_device_types" {
  description = "returns a list of string"
  value       = data.aws_ec2_instance_type.this.supported_root_device_types
}

output "supported_usages_classes" {
  description = "returns a list of string"
  value       = data.aws_ec2_instance_type.this.supported_usages_classes
}

output "supported_virtualization_types" {
  description = "returns a list of string"
  value       = data.aws_ec2_instance_type.this.supported_virtualization_types
}

output "sustained_clock_speed" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.sustained_clock_speed
}

output "total_fpga_memory" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.total_fpga_memory
}

output "total_gpu_memory" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.total_gpu_memory
}

output "total_instance_storage" {
  description = "returns a number"
  value       = data.aws_ec2_instance_type.this.total_instance_storage
}

output "valid_cores" {
  description = "returns a list of number"
  value       = data.aws_ec2_instance_type.this.valid_cores
}

output "valid_threads_per_core" {
  description = "returns a list of number"
  value       = data.aws_ec2_instance_type.this.valid_threads_per_core
}

output "this" {
  value = aws_ec2_instance_type.this
}
```

[top](#index)