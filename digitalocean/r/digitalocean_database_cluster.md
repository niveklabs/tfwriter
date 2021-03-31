# digitalocean_database_cluster

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
module "digitalocean_database_cluster" {
  source = "./modules/digitalocean/r/digitalocean_database_cluster"

  # engine - (required) is a type of string
  engine = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # name - (required) is a type of string
  name = null
  # node_count - (required) is a type of number
  node_count = null
  # private_network_uuid - (optional) is a type of string
  private_network_uuid = null
  # region - (required) is a type of string
  region = null
  # size - (required) is a type of string
  size = null
  # sql_mode - (optional) is a type of string
  sql_mode = null
  # tags - (optional) is a type of set of string
  tags = []
  # version - (optional) is a type of string
  version = null

  maintenance_window = [{
    day  = null
    hour = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "engine" {
  description = "(required)"
  type        = string
}

variable "eviction_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_count" {
  description = "(required)"
  type        = number
}

variable "private_network_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = string
}

variable "sql_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintenance_window" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      day  = string
      hour = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_database_cluster" "this" {
  engine               = var.engine
  eviction_policy      = var.eviction_policy
  name                 = var.name
  node_count           = var.node_count
  private_network_uuid = var.private_network_uuid
  region               = var.region
  size                 = var.size
  sql_mode             = var.sql_mode
  tags                 = var.tags
  version              = var.version

  dynamic "maintenance_window" {
    for_each = var.maintenance_window
    content {
      day  = maintenance_window.value["day"]
      hour = maintenance_window.value["hour"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "database" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.database
}

output "host" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.host
}

output "id" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.id
}

output "password" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = digitalocean_database_cluster.this.port
}

output "private_host" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.private_host
}

output "private_network_uuid" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.private_network_uuid
}

output "private_uri" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.private_uri
  sensitive   = true
}

output "uri" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.uri
  sensitive   = true
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.urn
}

output "user" {
  description = "returns a string"
  value       = digitalocean_database_cluster.this.user
}

output "this" {
  value = digitalocean_database_cluster.this
}
```

[top](#index)