# google_sql_ssl_cert

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_sql_ssl_cert" {
  source = "./modules/google/r/google_sql_ssl_cert"

  # common_name - (required) is a type of string
  common_name = null
  # instance - (required) is a type of string
  instance = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "common_name" {
  description = "(required) - The common name to be used in the certificate to identify the client. Constrained to [a-zA-Z.-_ ]+. Changing this forces a new resource to be created."
  type        = string
}

variable "instance" {
  description = "(required) - The name of the Cloud SQL instance. Changing this forces a new resource to be created."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
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
resource "google_sql_ssl_cert" "this" {
  # common_name - (required) is a type of string
  common_name = var.common_name
  # instance - (required) is a type of string
  instance = var.instance
  # project - (optional) is a type of string
  project = var.project

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
output "cert" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.cert
}

output "cert_serial_number" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.cert_serial_number
}

output "create_time" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.create_time
}

output "expiration_time" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.expiration_time
}

output "id" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.id
}

output "private_key" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.private_key
  sensitive   = true
}

output "project" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.project
}

output "server_ca_cert" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.server_ca_cert
}

output "sha1_fingerprint" {
  description = "returns a string"
  value       = google_sql_ssl_cert.this.sha1_fingerprint
}

output "this" {
  value = google_sql_ssl_cert.this
}
```

[top](#index)