# digitalocean_database_connection_pool

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
module "digitalocean_database_connection_pool" {
  source = "./modules/digitalocean/r/digitalocean_database_connection_pool"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # db_name - (required) is a type of string
  db_name = null
  # mode - (required) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # size - (required) is a type of number
  size = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "db_name" {
  description = "(required)"
  type        = string
}

variable "mode" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "user" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_database_connection_pool" "this" {
  cluster_id = var.cluster_id
  db_name    = var.db_name
  mode       = var.mode
  name       = var.name
  size       = var.size
  user       = var.user
}
```

[top](#index)

### Outputs

```terraform
output "host" {
  description = "returns a string"
  value       = digitalocean_database_connection_pool.this.host
}

output "id" {
  description = "returns a string"
  value       = digitalocean_database_connection_pool.this.id
}

output "password" {
  description = "returns a string"
  value       = digitalocean_database_connection_pool.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = digitalocean_database_connection_pool.this.port
}

output "private_host" {
  description = "returns a string"
  value       = digitalocean_database_connection_pool.this.private_host
}

output "private_uri" {
  description = "returns a string"
  value       = digitalocean_database_connection_pool.this.private_uri
  sensitive   = true
}

output "uri" {
  description = "returns a string"
  value       = digitalocean_database_connection_pool.this.uri
  sensitive   = true
}

output "this" {
  value = digitalocean_database_connection_pool.this
}
```

[top](#index)