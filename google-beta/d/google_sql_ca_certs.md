# google_sql_ca_certs

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_sql_ca_certs" {
  source = "./modules/google-beta/d/google_sql_ca_certs"

  # instance - (required) is a type of string
  instance = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "instance" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_sql_ca_certs" "this" {
  # instance - (required) is a type of string
  instance = var.instance
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "active_version" {
  description = "returns a string"
  value       = data.google_sql_ca_certs.this.active_version
}

output "certs" {
  description = "returns a list of object"
  value       = data.google_sql_ca_certs.this.certs
}

output "id" {
  description = "returns a string"
  value       = data.google_sql_ca_certs.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_sql_ca_certs.this.project
}

output "this" {
  value = google_sql_ca_certs.this
}
```

[top](#index)