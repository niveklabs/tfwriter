# alicloud_adb_clusters

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
module "alicloud_adb_clusters" {
  source = "./modules/alicloud/d/alicloud_adb_clusters"

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
data "alicloud_adb_clusters" "this" {
  # description_regex - (optional) is a type of string
  description_regex = var.description_regex
  # ids - (optional) is a type of list of string
  ids = var.ids
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # status - (optional) is a type of string
  status = var.status
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "clusters" {
  description = "returns a list of object"
  value       = data.alicloud_adb_clusters.this.clusters
}

output "descriptions" {
  description = "returns a list of string"
  value       = data.alicloud_adb_clusters.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_adb_clusters.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_adb_clusters.this.ids
}

output "this" {
  value = alicloud_adb_clusters.this
}
```

[top](#index)