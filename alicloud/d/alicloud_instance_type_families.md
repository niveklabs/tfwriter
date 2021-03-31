# alicloud_instance_type_families

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_instance_type_families" {
  source = "./modules/alicloud/d/alicloud_instance_type_families"

  # generation - (optional) is a type of string
  generation = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # spot_strategy - (optional) is a type of string
  spot_strategy = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "generation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_strategy" {
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
data "alicloud_instance_type_families" "this" {
  generation           = var.generation
  instance_charge_type = var.instance_charge_type
  output_file          = var.output_file
  spot_strategy        = var.spot_strategy
  zone_id              = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "families" {
  description = "returns a list of object"
  value       = data.alicloud_instance_type_families.this.families
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_instance_type_families.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_instance_type_families.this.ids
}

output "this" {
  value = alicloud_instance_type_families.this
}
```

[top](#index)