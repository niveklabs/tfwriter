# tencentcloud_tcaplus_idls

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
module "tencentcloud_tcaplus_idls" {
  source = "./modules/tencentcloud/d/tencentcloud_tcaplus_idls"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
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
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_tcaplus_idls" "this" {
  cluster_id         = var.cluster_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_tcaplus_idls.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_tcaplus_idls.this.list
}

output "this" {
  value = tencentcloud_tcaplus_idls.this
}
```

[top](#index)