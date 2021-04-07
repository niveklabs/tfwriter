# tencentcloud_tcaplus_table

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
module "tencentcloud_tcaplus_table" {
  source = "./modules/tencentcloud/r/tencentcloud_tcaplus_table"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # idl_id - (required) is a type of string
  idl_id = null
  # reserved_read_cu - (required) is a type of number
  reserved_read_cu = null
  # reserved_volume - (required) is a type of number
  reserved_volume = null
  # reserved_write_cu - (required) is a type of number
  reserved_write_cu = null
  # table_idl_type - (required) is a type of string
  table_idl_type = null
  # table_name - (required) is a type of string
  table_name = null
  # table_type - (required) is a type of string
  table_type = null
  # tablegroup_id - (required) is a type of string
  tablegroup_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the TcaplusDB cluster to which the table belongs."
  type        = string
}

variable "description" {
  description = "(optional) - Description of the TcaplusDB table."
  type        = string
  default     = null
}

variable "idl_id" {
  description = "(required) - ID of the IDL File."
  type        = string
}

variable "reserved_read_cu" {
  description = "(required) - Reserved read capacity units of the TcaplusDB table."
  type        = number
}

variable "reserved_volume" {
  description = "(required) - Reserved storage capacity of the TcaplusDB table (unit: GB)."
  type        = number
}

variable "reserved_write_cu" {
  description = "(required) - Reserved write capacity units of the TcaplusDB table."
  type        = number
}

variable "table_idl_type" {
  description = "(required) - IDL type of the TcaplusDB table. Valid values: `PROTO` and `TDR`."
  type        = string
}

variable "table_name" {
  description = "(required) - Name of the TcaplusDB table."
  type        = string
}

variable "table_type" {
  description = "(required) - Type of the TcaplusDB table. Valid values are `GENERIC` and `LIST`."
  type        = string
}

variable "tablegroup_id" {
  description = "(required) - ID of the table group to which the table belongs."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcaplus_table" "this" {
  cluster_id        = var.cluster_id
  description       = var.description
  idl_id            = var.idl_id
  reserved_read_cu  = var.reserved_read_cu
  reserved_volume   = var.reserved_volume
  reserved_write_cu = var.reserved_write_cu
  table_idl_type    = var.table_idl_type
  table_name        = var.table_name
  table_type        = var.table_type
  tablegroup_id     = var.tablegroup_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_table.this.create_time
}

output "error" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_table.this.error
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_table.this.id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_table.this.status
}

output "table_size" {
  description = "returns a number"
  value       = tencentcloud_tcaplus_table.this.table_size
}

output "this" {
  value = tencentcloud_tcaplus_table.this
}
```

[top](#index)