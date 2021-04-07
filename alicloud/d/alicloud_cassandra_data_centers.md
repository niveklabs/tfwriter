# alicloud_cassandra_data_centers

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
module "alicloud_cassandra_data_centers" {
  source = "./modules/alicloud/d/alicloud_cassandra_data_centers"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cassandra_data_centers" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "centers" {
  description = "returns a list of object"
  value       = data.alicloud_cassandra_data_centers.this.centers
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cassandra_data_centers.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cassandra_data_centers.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cassandra_data_centers.this.names
}

output "this" {
  value = alicloud_cassandra_data_centers.this
}
```

[top](#index)