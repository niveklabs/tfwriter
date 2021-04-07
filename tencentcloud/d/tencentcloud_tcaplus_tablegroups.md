# tencentcloud_tcaplus_tablegroups

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
module "tencentcloud_tcaplus_tablegroups" {
  source = "./modules/tencentcloud/d/tencentcloud_tcaplus_tablegroups"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tablegroup_id - (optional) is a type of string
  tablegroup_id = null
  # tablegroup_name - (optional) is a type of string
  tablegroup_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - Id of the TcaplusDB cluster to be query."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - File for saving results."
  type        = string
  default     = null
}

variable "tablegroup_id" {
  description = "(optional) - Id of the table group to be query."
  type        = string
  default     = null
}

variable "tablegroup_name" {
  description = "(optional) - Name of the table group to be query."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_tcaplus_tablegroups" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tablegroup_id - (optional) is a type of string
  tablegroup_id = var.tablegroup_id
  # tablegroup_name - (optional) is a type of string
  tablegroup_name = var.tablegroup_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_tcaplus_tablegroups.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_tcaplus_tablegroups.this.list
}

output "this" {
  value = tencentcloud_tcaplus_tablegroups.this
}
```

[top](#index)