# alicloud_polardb_endpoints

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
module "alicloud_polardb_endpoints" {
  source = "./modules/alicloud/d/alicloud_polardb_endpoints"

  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # db_endpoint_id - (optional) is a type of string
  db_endpoint_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "db_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_polardb_endpoints" "this" {
  # db_cluster_id - (required) is a type of string
  db_cluster_id = var.db_cluster_id
  # db_endpoint_id - (optional) is a type of string
  db_endpoint_id = var.db_endpoint_id
}
```

[top](#index)

### Outputs

```terraform
output "endpoints" {
  description = "returns a list of object"
  value       = data.alicloud_polardb_endpoints.this.endpoints
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_polardb_endpoints.this.id
}

output "this" {
  value = alicloud_polardb_endpoints.this
}
```

[top](#index)