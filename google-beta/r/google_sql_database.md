# google_sql_database

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_sql_database" {
  source = "./modules/google-beta/r/google_sql_database"

  # charset - (optional) is a type of string
  charset = null
  # collation - (optional) is a type of string
  collation = null
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
variable "charset" {
  description = "(optional) - The charset value. See MySQL's\n[Supported Character Sets and Collations](https://dev.mysql.com/doc/refman/5.7/en/charset-charsets.html)\nand Postgres' [Character Set Support](https://www.postgresql.org/docs/9.6/static/multibyte.html)\nfor more details and supported values. Postgres databases only support\na value of 'UTF8' at creation time."
  type        = string
  default     = null
}

variable "collation" {
  description = "(optional) - The collation value. See MySQL's\n[Supported Character Sets and Collations](https://dev.mysql.com/doc/refman/5.7/en/charset-charsets.html)\nand Postgres' [Collation Support](https://www.postgresql.org/docs/9.6/static/collation.html)\nfor more details and supported values. Postgres databases only support\na value of 'en_US.UTF8' at creation time."
  type        = string
  default     = null
}

variable "instance" {
  description = "(required) - The name of the Cloud SQL instance. This does not include the project\nID."
  type        = string
}

variable "name" {
  description = "(required) - The name of the database in the Cloud SQL instance.\nThis does not include the project ID or instance name."
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
resource "google_sql_database" "this" {
  charset   = var.charset
  collation = var.collation
  instance  = var.instance
  name      = var.name
  project   = var.project

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
output "charset" {
  description = "returns a string"
  value       = google_sql_database.this.charset
}

output "collation" {
  description = "returns a string"
  value       = google_sql_database.this.collation
}

output "id" {
  description = "returns a string"
  value       = google_sql_database.this.id
}

output "project" {
  description = "returns a string"
  value       = google_sql_database.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_sql_database.this.self_link
}

output "this" {
  value = google_sql_database.this
}
```

[top](#index)