# aws_msk_cluster

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_msk_cluster" {
  source = "./modules/aws/d/aws_msk_cluster"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
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
data "aws_msk_cluster" "this" {
  cluster_name = var.cluster_name
  tags         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.arn
}

output "bootstrap_brokers" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.bootstrap_brokers
}

output "bootstrap_brokers_sasl_scram" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.bootstrap_brokers_sasl_scram
}

output "bootstrap_brokers_tls" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.bootstrap_brokers_tls
}

output "id" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.id
}

output "kafka_version" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.kafka_version
}

output "number_of_broker_nodes" {
  description = "returns a number"
  value       = data.aws_msk_cluster.this.number_of_broker_nodes
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_msk_cluster.this.tags
}

output "zookeeper_connect_string" {
  description = "returns a string"
  value       = data.aws_msk_cluster.this.zookeeper_connect_string
}

output "this" {
  value = aws_msk_cluster.this
}
```

[top](#index)