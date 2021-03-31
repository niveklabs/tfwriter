# digitalocean_database_cluster

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_database_cluster" {
  source = "./modules/digitalocean/d/digitalocean_database_cluster"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_database_cluster" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "database" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.database
}

output "engine" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.engine
}

output "host" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.host
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.id
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = data.digitalocean_database_cluster.this.maintenance_window
}

output "node_count" {
  description = "returns a number"
  value       = data.digitalocean_database_cluster.this.node_count
}

output "password" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = data.digitalocean_database_cluster.this.port
}

output "private_host" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.private_host
}

output "private_network_uuid" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.private_network_uuid
}

output "private_uri" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.private_uri
  sensitive   = true
}

output "region" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.region
}

output "size" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.size
}

output "uri" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.uri
  sensitive   = true
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.urn
}

output "user" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.user
}

output "version" {
  description = "returns a string"
  value       = data.digitalocean_database_cluster.this.version
}

output "this" {
  value = digitalocean_database_cluster.this
}
```

[top](#index)