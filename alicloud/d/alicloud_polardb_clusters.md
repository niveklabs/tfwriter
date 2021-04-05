# alicloud_polardb_clusters

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
module "alicloud_polardb_clusters" {
  source = "./modules/alicloud/d/alicloud_polardb_clusters"

  # db_type - (optional) is a type of string
  db_type = null
  # description_regex - (optional) is a type of string
  description_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "db_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_polardb_clusters" "this" {
  db_type           = var.db_type
  description_regex = var.description_regex
  ids               = var.ids
  output_file       = var.output_file
  status            = var.status
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "clusters" {
  description = "returns a list of object"
  value       = data.alicloud_polardb_clusters.this.clusters
}

output "descriptions" {
  description = "returns a list of string"
  value       = data.alicloud_polardb_clusters.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_polardb_clusters.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_polardb_clusters.this.ids
}

output "this" {
  value = alicloud_polardb_clusters.this
}
```

[top](#index)