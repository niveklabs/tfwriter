# tencentcloud_tcaplus_idl

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
module "tencentcloud_tcaplus_idl" {
  source = "./modules/tencentcloud/r/tencentcloud_tcaplus_idl"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # file_content - (required) is a type of string
  file_content = null
  # file_ext_type - (required) is a type of string
  file_ext_type = null
  # file_name - (required) is a type of string
  file_name = null
  # file_type - (required) is a type of string
  file_type = null
  # tablegroup_id - (required) is a type of string
  tablegroup_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the TcaplusDB cluster to which the table group belongs."
  type        = string
}

variable "file_content" {
  description = "(required) - IDL file content of the TcaplusDB table."
  type        = string
}

variable "file_ext_type" {
  description = "(required) - File ext type of the IDL file. If `file_type` is `PROTO`, `file_ext_type` must be 'proto'; If `file_type` is `TDR`, `file_ext_type` must be 'xml'."
  type        = string
}

variable "file_name" {
  description = "(required) - Name of the IDL file."
  type        = string
}

variable "file_type" {
  description = "(required) - Type of the IDL file. Valid values are PROTO and TDR."
  type        = string
}

variable "tablegroup_id" {
  description = "(required) - ID of the table group to which the IDL file belongs."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcaplus_idl" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # file_content - (required) is a type of string
  file_content = var.file_content
  # file_ext_type - (required) is a type of string
  file_ext_type = var.file_ext_type
  # file_name - (required) is a type of string
  file_name = var.file_name
  # file_type - (required) is a type of string
  file_type = var.file_type
  # tablegroup_id - (required) is a type of string
  tablegroup_id = var.tablegroup_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_tcaplus_idl.this.id
}

output "table_infos" {
  description = "returns a list of object"
  value       = tencentcloud_tcaplus_idl.this.table_infos
}

output "this" {
  value = tencentcloud_tcaplus_idl.this
}
```

[top](#index)