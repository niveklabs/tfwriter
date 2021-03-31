# digitalocean_database_replica

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "digitalocean_database_replica" {
  source = "./modules/digitalocean/r/digitalocean_database_replica"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null
  # private_network_uuid - (optional) is a type of string
  private_network_uuid = null
  # region - (optional) is a type of string
  region = null
  # size - (optional) is a type of string
  size = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "private_network_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_database_replica" "this" {
  cluster_id           = var.cluster_id
  name                 = var.name
  private_network_uuid = var.private_network_uuid
  region               = var.region
  size                 = var.size
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "database" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.database
}

output "host" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.host
}

output "id" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.id
}

output "password" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = digitalocean_database_replica.this.port
}

output "private_host" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.private_host
}

output "private_network_uuid" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.private_network_uuid
}

output "private_uri" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.private_uri
  sensitive   = true
}

output "uri" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.uri
  sensitive   = true
}

output "user" {
  description = "returns a string"
  value       = digitalocean_database_replica.this.user
}

output "this" {
  value = digitalocean_database_replica.this
}
```

[top](#index)