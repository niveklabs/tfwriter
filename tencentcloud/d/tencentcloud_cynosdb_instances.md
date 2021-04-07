# tencentcloud_cynosdb_instances

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
module "tencentcloud_cynosdb_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_cynosdb_instances"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # db_type - (optional) is a type of string
  db_type = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional) - ID of the cluster."
  type        = string
  default     = null
}

variable "db_type" {
  description = "(optional) - Type of CynosDB, and available values include `MYSQL`, `POSTGRESQL`."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional) - ID of the Cynosdb instance to be queried."
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional) - Name of the Cynosdb instance to be queried."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project to be queried."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cynosdb_instances" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # db_type - (optional) is a type of string
  db_type = var.db_type
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cynosdb_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cynosdb_instances.this.instance_list
}

output "this" {
  value = tencentcloud_cynosdb_instances.this
}
```

[top](#index)