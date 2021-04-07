# tencentcloud_tcaplus_tables

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
module "tencentcloud_tcaplus_tables" {
  source = "./modules/tencentcloud/d/tencentcloud_tcaplus_tables"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # table_id - (optional) is a type of string
  table_id = null
  # table_name - (optional) is a type of string
  table_name = null
  # tablegroup_id - (optional) is a type of string
  tablegroup_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the TcaplusDB cluster to be query."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - File for saving results."
  type        = string
  default     = null
}

variable "table_id" {
  description = "(optional) - Table ID to be query."
  type        = string
  default     = null
}

variable "table_name" {
  description = "(optional) - Table name to be query."
  type        = string
  default     = null
}

variable "tablegroup_id" {
  description = "(optional) - ID of the table group to be query."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_tcaplus_tables" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # table_id - (optional) is a type of string
  table_id = var.table_id
  # table_name - (optional) is a type of string
  table_name = var.table_name
  # tablegroup_id - (optional) is a type of string
  tablegroup_id = var.tablegroup_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_tcaplus_tables.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_tcaplus_tables.this.list
}

output "this" {
  value = tencentcloud_tcaplus_tables.this
}
```

[top](#index)