# tencentcloud_tcaplus_tablegroup

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
module "tencentcloud_tcaplus_tablegroup" {
  source = "./modules/tencentcloud/r/tencentcloud_tcaplus_tablegroup"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # tablegroup_name - (required) is a type of string
  tablegroup_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the TcaplusDB cluster to which the table group belongs."
  type        = string
}

variable "tablegroup_name" {
  description = "(required) - Name of the TcaplusDB table group. Name length should be between 1 and 30."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcaplus_tablegroup" "this" {
  cluster_id      = var.cluster_id
  tablegroup_name = var.tablegroup_name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_tablegroup.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_tablegroup.this.id
}

output "table_count" {
  description = "returns a number"
  value       = tencentcloud_tcaplus_tablegroup.this.table_count
}

output "total_size" {
  description = "returns a number"
  value       = tencentcloud_tcaplus_tablegroup.this.total_size
}

output "this" {
  value = tencentcloud_tcaplus_tablegroup.this
}
```

[top](#index)