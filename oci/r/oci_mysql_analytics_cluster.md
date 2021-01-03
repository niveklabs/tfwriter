# oci_mysql_analytics_cluster

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_mysql_analytics_cluster" {
  source = "./modules/oci/r/oci_mysql_analytics_cluster"

  # cluster_size - (required) is a type of number
  cluster_size = null
  # db_system_id - (required) is a type of string
  db_system_id = null
  # shape_name - (required) is a type of string
  shape_name = null
  # state - (optional) is a type of string
  state = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_size" {
  description = "(required)"
  type        = number
}

variable "db_system_id" {
  description = "(required)"
  type        = string
}

variable "shape_name" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_mysql_analytics_cluster" "this" {
  cluster_size = var.cluster_size
  db_system_id = var.db_system_id
  shape_name   = var.shape_name
  state        = var.state

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_nodes" {
  description = "returns a list of object"
  value       = oci_mysql_analytics_cluster.this.cluster_nodes
}

output "id" {
  description = "returns a string"
  value       = oci_mysql_analytics_cluster.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_mysql_analytics_cluster.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_mysql_analytics_cluster.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_mysql_analytics_cluster.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_mysql_analytics_cluster.this.time_updated
}

output "this" {
  value = oci_mysql_analytics_cluster.this
}
```

[top](#index)