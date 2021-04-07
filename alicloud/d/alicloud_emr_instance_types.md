# alicloud_emr_instance_types

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_emr_instance_types" {
  source = "./modules/alicloud/d/alicloud_emr_instance_types"

  # cluster_type - (required) is a type of string
  cluster_type = null
  # destination_resource - (required) is a type of string
  destination_resource = null
  # instance_charge_type - (required) is a type of string
  instance_charge_type = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # support_local_storage - (optional) is a type of bool
  support_local_storage = null
  # support_node_type - (optional) is a type of list of string
  support_node_type = []
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "support_local_storage" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "support_node_type" {
  description = "(optional)"
  type        = list(string)
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
data "alicloud_emr_instance_types" "this" {
  # cluster_type - (required) is a type of string
  cluster_type = var.cluster_type
  # destination_resource - (required) is a type of string
  destination_resource = var.destination_resource
  # instance_charge_type - (required) is a type of string
  instance_charge_type = var.instance_charge_type
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # support_local_storage - (optional) is a type of bool
  support_local_storage = var.support_local_storage
  # support_node_type - (optional) is a type of list of string
  support_node_type = var.support_node_type
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_emr_instance_types.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_emr_instance_types.this.ids
}

output "types" {
  description = "returns a list of object"
  value       = data.alicloud_emr_instance_types.this.types
}

output "this" {
  value = alicloud_emr_instance_types.this
}
```

[top](#index)