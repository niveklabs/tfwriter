# aws_redshift_orderable_cluster

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_redshift_orderable_cluster" {
  source = "./modules/aws/d/aws_redshift_orderable_cluster"

  # cluster_type - (optional) is a type of string
  cluster_type = null
  # cluster_version - (optional) is a type of string
  cluster_version = null
  # node_type - (optional) is a type of string
  node_type = null
  # preferred_node_types - (optional) is a type of list of string
  preferred_node_types = []
}
```

[top](#index)

### Variables

```terraform
variable "cluster_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_node_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_redshift_orderable_cluster" "this" {
  cluster_type         = var.cluster_type
  cluster_version      = var.cluster_version
  node_type            = var.node_type
  preferred_node_types = var.preferred_node_types
}
```

[top](#index)

### Outputs

```terraform
output "availability_zones" {
  description = "returns a list of string"
  value       = data.aws_redshift_orderable_cluster.this.availability_zones
}

output "cluster_type" {
  description = "returns a string"
  value       = data.aws_redshift_orderable_cluster.this.cluster_type
}

output "cluster_version" {
  description = "returns a string"
  value       = data.aws_redshift_orderable_cluster.this.cluster_version
}

output "id" {
  description = "returns a string"
  value       = data.aws_redshift_orderable_cluster.this.id
}

output "node_type" {
  description = "returns a string"
  value       = data.aws_redshift_orderable_cluster.this.node_type
}

output "this" {
  value = aws_redshift_orderable_cluster.this
}
```

[top](#index)