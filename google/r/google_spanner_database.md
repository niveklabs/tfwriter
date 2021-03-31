# google_spanner_database

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_spanner_database" {
  source = "./modules/google/r/google_spanner_database"

  # ddl - (optional) is a type of list of string
  ddl = []
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # instance - (required) is a type of string
  instance = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

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
variable "ddl" {
  description = "(optional) - An optional list of DDL statements to run inside the newly created\ndatabase. Statements can create tables, indexes, etc. These statements\nexecute atomically with the creation of the database: if there is an\nerror in any statement, the database is not created."
  type        = list(string)
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance" {
  description = "(required) - The instance to create the database on."
  type        = string
}

variable "name" {
  description = "(required) - A unique identifier for the database, which cannot be changed after\nthe instance is created. Values are of the form [a-z][-a-z0-9]*[a-z0-9]."
  type        = string
}

variable "project" {
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
resource "google_spanner_database" "this" {
  ddl                 = var.ddl
  deletion_protection = var.deletion_protection
  instance            = var.instance
  name                = var.name
  project             = var.project

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
output "id" {
  description = "returns a string"
  value       = google_spanner_database.this.id
}

output "project" {
  description = "returns a string"
  value       = google_spanner_database.this.project
}

output "state" {
  description = "returns a string"
  value       = google_spanner_database.this.state
}

output "this" {
  value = google_spanner_database.this
}
```

[top](#index)