# ecl_storage_volume_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_storage_volume_v1" {
  source = "./modules/ecl/d/ecl_storage_volume_v1"

  # name - (optional) is a type of string
  name = null
  # volume_id - (optional) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_storage_volume_v1" "this" {
  name      = var.name
  volume_id = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = data.ecl_storage_volume_v1.this.availability_zone
}

output "description" {
  description = "returns a string"
  value       = data.ecl_storage_volume_v1.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_storage_volume_v1.this.id
}

output "initiator_iqns" {
  description = "returns a set of string"
  value       = data.ecl_storage_volume_v1.this.initiator_iqns
}

output "iops_per_gb" {
  description = "returns a string"
  value       = data.ecl_storage_volume_v1.this.iops_per_gb
}

output "size" {
  description = "returns a number"
  value       = data.ecl_storage_volume_v1.this.size
}

output "throughput" {
  description = "returns a string"
  value       = data.ecl_storage_volume_v1.this.throughput
}

output "virtual_storage_id" {
  description = "returns a string"
  value       = data.ecl_storage_volume_v1.this.virtual_storage_id
}

output "this" {
  value = ecl_storage_volume_v1.this
}
```

[top](#index)