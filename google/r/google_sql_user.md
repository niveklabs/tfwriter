# google_sql_user

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_sql_user" {
  source = "./modules/google/r/google_sql_user"

  # deletion_policy - (optional) is a type of string
  deletion_policy = null
  # host - (optional) is a type of string
  host = null
  # instance - (required) is a type of string
  instance = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
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

```hcl
variable "deletion_policy" {
  description = "(optional) - The deletion policy for the user. Setting ABANDON allows the resource\n\t\t\t\tto be abandoned rather than deleted. This is useful for Postgres, where users cannot be deleted from the API if they\n\t\t\t\thave been granted SQL roles. Possible values are: \"ABANDON\"."
  type        = string
  default     = null
}

variable "host" {
  description = "(optional) - The host the user can connect from. This is only supported for MySQL instances. Don't set this field for PostgreSQL instances. Can be an IP address. Changing this forces a new resource to be created."
  type        = string
  default     = null
}

variable "instance" {
  description = "(required) - The name of the Cloud SQL instance. Changing this forces a new resource to be created."
  type        = string
}

variable "name" {
  description = "(required) - The name of the user. Changing this forces a new resource to be created."
  type        = string
}

variable "password" {
  description = "(optional) - The password for the user. Can be updated. For Postgres instances this is a Required field."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_sql_user" "this" {
  deletion_policy = var.deletion_policy
  host            = var.host
  instance        = var.instance
  name            = var.name
  password        = var.password
  project         = var.project

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_sql_user.this.id
}

output "project" {
  description = "returns a string"
  value       = google_sql_user.this.project
}

output "this" {
  value = google_sql_user.this
}
```

[top](#index)