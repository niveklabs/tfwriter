# digitalocean_database_db

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
module "digitalocean_database_db" {
  source = "./modules/digitalocean/r/digitalocean_database_db"

  # cluster_id - (required) is a type of string
  cluster_id = null
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

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_database_db" "this" {
  cluster_id = var.cluster_id
  name       = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_database_db.this.id
}

output "this" {
  value = digitalocean_database_db.this
}
```

[top](#index)