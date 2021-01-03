# alicloud_instance_types

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_instance_types" {
  source = "./modules/alicloud/d/alicloud_instance_types"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cpu_core_count - (optional) is a type of number
  cpu_core_count = null
  # eni_amount - (optional) is a type of number
  eni_amount = null
  # gpu_amount - (optional) is a type of number
  gpu_amount = null
  # gpu_spec - (optional) is a type of string
  gpu_spec = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_type_family - (optional) is a type of string
  instance_type_family = null
  # is_outdated - (optional) is a type of bool
  is_outdated = null
  # kubernetes_node_role - (optional) is a type of string
  kubernetes_node_role = null
  # memory_size - (optional) is a type of number
  memory_size = null
  # network_type - (optional) is a type of string
  network_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # sorted_by - (optional) is a type of string
  sorted_by = null
  # spot_strategy - (optional) is a type of string
  spot_strategy = null
}
```

[top](#index)

### Variables

```terraform
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

variable "eni_amount" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gpu_amount" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gpu_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_outdated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kubernetes_node_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sorted_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_instance_types" "this" {
  availability_zone    = var.availability_zone
  cpu_core_count       = var.cpu_core_count
  eni_amount           = var.eni_amount
  gpu_amount           = var.gpu_amount
  gpu_spec             = var.gpu_spec
  instance_charge_type = var.instance_charge_type
  instance_type_family = var.instance_type_family
  is_outdated          = var.is_outdated
  kubernetes_node_role = var.kubernetes_node_role
  memory_size          = var.memory_size
  network_type         = var.network_type
  output_file          = var.output_file
  sorted_by            = var.sorted_by
  spot_strategy        = var.spot_strategy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_instance_types.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_instance_types.this.ids
}

output "instance_types" {
  description = "returns a list of object"
  value       = data.alicloud_instance_types.this.instance_types
}

output "this" {
  value = alicloud_instance_types.this
}
```

[top](#index)