# tencentcloud_mongodb_instances

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_mongodb_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_mongodb_instances"

  # cluster_type - (optional) is a type of string
  cluster_type = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # instance_name_prefix - (optional) is a type of string
  instance_name_prefix = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "cluster_type" {
  description = "(optional) - Type of Mongodb cluster, and available values include replica set cluster(expressed with `REPLSET`), sharding cluster(expressed with `SHARD`)."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional) - ID of the Mongodb instance to be queried."
  type        = string
  default     = null
}

variable "instance_name_prefix" {
  description = "(optional) - Name prefix of the Mongodb instance."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the Mongodb instance to be queried."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_mongodb_instances" "this" {
  # cluster_type - (optional) is a type of string
  cluster_type = var.cluster_type
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # instance_name_prefix - (optional) is a type of string
  instance_name_prefix = var.instance_name_prefix
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_mongodb_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_mongodb_instances.this.instance_list
}

output "this" {
  value = tencentcloud_mongodb_instances.this
}
```

[top](#index)