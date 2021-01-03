# digitalocean_database_user

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
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_database_user" {
  source = "./modules/digitalocean/r/digitalocean_database_user"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # mysql_auth_plugin - (optional) is a type of string
  mysql_auth_plugin = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "mysql_auth_plugin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_database_user" "this" {
  cluster_id        = var.cluster_id
  mysql_auth_plugin = var.mysql_auth_plugin
  name              = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_database_user.this.id
}

output "password" {
  description = "returns a string"
  value       = digitalocean_database_user.this.password
  sensitive   = true
}

output "role" {
  description = "returns a string"
  value       = digitalocean_database_user.this.role
}

output "this" {
  value = digitalocean_database_user.this
}
```

[top](#index)