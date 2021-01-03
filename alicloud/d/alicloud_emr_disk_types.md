# alicloud_emr_disk_types

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
module "alicloud_emr_disk_types" {
  source = "./modules/alicloud/d/alicloud_emr_disk_types"

  # cluster_type - (required) is a type of string
  cluster_type = null
  # destination_resource - (required) is a type of string
  destination_resource = null
  # instance_charge_type - (required) is a type of string
  instance_charge_type = null
  # instance_type - (required) is a type of string
  instance_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_type" {
  description = "(required)"
  type        = string
}

variable "destination_resource" {
  description = "(required)"
  type        = string
}

variable "instance_charge_type" {
  description = "(required)"
  type        = string
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_emr_disk_types" "this" {
  cluster_type         = var.cluster_type
  destination_resource = var.destination_resource
  instance_charge_type = var.instance_charge_type
  instance_type        = var.instance_type
  output_file          = var.output_file
  zone_id              = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_emr_disk_types.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_emr_disk_types.this.ids
}

output "types" {
  description = "returns a list of object"
  value       = data.alicloud_emr_disk_types.this.types
}

output "this" {
  value = alicloud_emr_disk_types.this
}
```

[top](#index)