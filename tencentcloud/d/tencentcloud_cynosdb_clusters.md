# tencentcloud_cynosdb_clusters

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
module "tencentcloud_cynosdb_clusters" {
  source = "./modules/tencentcloud/d/tencentcloud_cynosdb_clusters"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
  # db_type - (optional) is a type of string
  db_type = null
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
  description = "(optional) - ID of the cluster to be queried."
  type        = string
  default     = null
}

variable "cluster_name" {
  description = "(optional) - Name of the cluster to be queried."
  type        = string
  default     = null
}

variable "db_type" {
  description = "(optional) - Type of CynosDB, and available values include `MYSQL`, `POSTGRESQL`."
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
data "tencentcloud_cynosdb_clusters" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # cluster_name - (optional) is a type of string
  cluster_name = var.cluster_name
  # db_type - (optional) is a type of string
  db_type = var.db_type
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "cluster_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cynosdb_clusters.this.cluster_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cynosdb_clusters.this.id
}

output "this" {
  value = tencentcloud_cynosdb_clusters.this
}
```

[top](#index)