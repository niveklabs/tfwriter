# tencentcloud_cynosdb_readonly_instance

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cynosdb_readonly_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_cynosdb_readonly_instance"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # instance_cpu_core - (required) is a type of number
  instance_cpu_core = null
  # instance_maintain_duration - (optional) is a type of number
  instance_maintain_duration = null
  # instance_maintain_start_time - (optional) is a type of number
  instance_maintain_start_time = null
  # instance_maintain_weekdays - (optional) is a type of set of string
  instance_maintain_weekdays = []
  # instance_memory_size - (required) is a type of number
  instance_memory_size = null
  # instance_name - (required) is a type of string
  instance_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - Cluster ID which the readonly instance belongs to."
  type        = string
}

variable "force_delete" {
  description = "(optional) - Indicate whether to delete readonly instance directly or not. Default is false. If set true, instance will be deleted instead of staying recycle bin. Note: works for both `PREPAID` and `POSTPAID_BY_HOUR` cluster."
  type        = bool
  default     = null
}

variable "instance_cpu_core" {
  description = "(required) - The number of CPU cores of read-write type instance in the CynosDB cluster. Note: modification of this field will take effect immediately, if want to upgrade on maintenance window, please upgrade from console."
  type        = number
}

variable "instance_maintain_duration" {
  description = "(optional) - Duration time for maintenance, unit in second. `3600` by default."
  type        = number
  default     = null
}

variable "instance_maintain_start_time" {
  description = "(optional) - Offset time from 00:00, unit in second. For example, 03:00am should be `10800`. `10800` by default."
  type        = number
  default     = null
}

variable "instance_maintain_weekdays" {
  description = "(optional) - Weekdays for maintenance. `[\"Mon\", \"Tue\", \"Wed\", \"Thu\", \"Fri\", \"Sat\", \"Sun\"]` by default."
  type        = set(string)
  default     = null
}

variable "instance_memory_size" {
  description = "(required) - Memory capacity of read-write type instance, unit in GB. Note: modification of this field will take effect immediately, if want to upgrade on maintenance window, please upgrade from console."
  type        = number
}

variable "instance_name" {
  description = "(required) - Name of instance."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cynosdb_readonly_instance" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # instance_cpu_core - (required) is a type of number
  instance_cpu_core = var.instance_cpu_core
  # instance_maintain_duration - (optional) is a type of number
  instance_maintain_duration = var.instance_maintain_duration
  # instance_maintain_start_time - (optional) is a type of number
  instance_maintain_start_time = var.instance_maintain_start_time
  # instance_maintain_weekdays - (optional) is a type of set of string
  instance_maintain_weekdays = var.instance_maintain_weekdays
  # instance_memory_size - (required) is a type of number
  instance_memory_size = var.instance_memory_size
  # instance_name - (required) is a type of string
  instance_name = var.instance_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_readonly_instance.this.id
}

output "instance_maintain_weekdays" {
  description = "returns a set of string"
  value       = tencentcloud_cynosdb_readonly_instance.this.instance_maintain_weekdays
}

output "instance_status" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_readonly_instance.this.instance_status
}

output "instance_storage_size" {
  description = "returns a number"
  value       = tencentcloud_cynosdb_readonly_instance.this.instance_storage_size
}

output "this" {
  value = tencentcloud_cynosdb_readonly_instance.this
}
```

[top](#index)