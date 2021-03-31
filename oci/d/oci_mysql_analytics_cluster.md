# oci_mysql_analytics_cluster

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_mysql_analytics_cluster" {
  source = "./modules/oci/d/oci_mysql_analytics_cluster"

  # db_system_id - (required) is a type of string
  db_system_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_system_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_mysql_analytics_cluster" "this" {
  db_system_id = var.db_system_id
}
```

[top](#index)

### Outputs

```terraform
output "cluster_nodes" {
  description = "returns a list of object"
  value       = data.oci_mysql_analytics_cluster.this.cluster_nodes
}

output "cluster_size" {
  description = "returns a number"
  value       = data.oci_mysql_analytics_cluster.this.cluster_size
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_analytics_cluster.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_mysql_analytics_cluster.this.lifecycle_details
}

output "shape_name" {
  description = "returns a string"
  value       = data.oci_mysql_analytics_cluster.this.shape_name
}

output "state" {
  description = "returns a string"
  value       = data.oci_mysql_analytics_cluster.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_mysql_analytics_cluster.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_mysql_analytics_cluster.this.time_updated
}

output "this" {
  value = oci_mysql_analytics_cluster.this
}
```

[top](#index)