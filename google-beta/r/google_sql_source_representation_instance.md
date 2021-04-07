# google_sql_source_representation_instance

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
module "google_sql_source_representation_instance" {
  source = "./modules/google-beta/r/google_sql_source_representation_instance"

  # database_version - (required) is a type of string
  database_version = null
  # host - (required) is a type of string
  host = null
  # name - (required) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "database_version" {
  description = "(required) - The MySQL version running on your source database server. Possible values: [\"MYSQL_5_5\", \"MYSQL_5_6\", \"MYSQL_5_7\", \"MYSQL_8_0\"]"
  type        = string
}

variable "host" {
  description = "(required) - The externally accessible IPv4 address for the source database server."
  type        = string
}

variable "name" {
  description = "(required) - The name of the source representation instance. Use any valid Cloud SQL instance name."
  type        = string
}

variable "port" {
  description = "(optional) - The externally accessible port for the source database server.\nDefaults to 3306."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the created instance should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_sql_source_representation_instance" "this" {
  # database_version - (required) is a type of string
  database_version = var.database_version
  # host - (required) is a type of string
  host = var.host
  # name - (required) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_sql_source_representation_instance.this.id
}

output "project" {
  description = "returns a string"
  value       = google_sql_source_representation_instance.this.project
}

output "region" {
  description = "returns a string"
  value       = google_sql_source_representation_instance.this.region
}

output "this" {
  value = google_sql_source_representation_instance.this
}
```

[top](#index)