# aws_cloudhsm_v2_cluster

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_cloudhsm_v2_cluster" {
  source = "./modules/aws/d/aws_cloudhsm_v2_cluster"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # cluster_state - (optional) is a type of string
  cluster_state = null
}
```

[top](#index)

### Variables

```hcl
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "cluster_state" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_cloudhsm_v2_cluster" "this" {
  cluster_id    = var.cluster_id
  cluster_state = var.cluster_state
}
```

[top](#index)

### Outputs

```hcl
output "cluster_certificates" {
  description = "returns a list of object"
  value       = data.aws_cloudhsm_v2_cluster.this.cluster_certificates
}

output "cluster_state" {
  description = "returns a string"
  value       = data.aws_cloudhsm_v2_cluster.this.cluster_state
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudhsm_v2_cluster.this.id
}

output "security_group_id" {
  description = "returns a string"
  value       = data.aws_cloudhsm_v2_cluster.this.security_group_id
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = data.aws_cloudhsm_v2_cluster.this.subnet_ids
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_cloudhsm_v2_cluster.this.vpc_id
}

output "this" {
  value = aws_cloudhsm_v2_cluster.this
}
```

[top](#index)