# google_compute_managed_ssl_certificate

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_managed_ssl_certificate" {
  source = "./modules/google/r/google_compute_managed_ssl_certificate"

  # certificate_id - (optional) is a type of number
  certificate_id = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # type - (optional) is a type of string
  type = null

  managed = [{
    domains = []
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(optional) - The unique identifier for the resource."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash.\n\n\nThese are in the same namespace as the managed SSL certificates."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Enum field whose value is always 'MANAGED' - used to signal to the API\nwhich type this is. Default value: \"MANAGED\" Possible values: [\"MANAGED\"]"
  type        = string
  default     = null
}

variable "managed" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      domains = list(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
resource "google_compute_managed_ssl_certificate" "this" {
  certificate_id = var.certificate_id
  description    = var.description
  name           = var.name
  project        = var.project
  type           = var.type

  dynamic "managed" {
    for_each = var.managed
    content {
      domains = managed.value["domains"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate_id" {
  description = "returns a number"
  value       = google_compute_managed_ssl_certificate.this.certificate_id
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_managed_ssl_certificate.this.creation_timestamp
}

output "expire_time" {
  description = "returns a string"
  value       = google_compute_managed_ssl_certificate.this.expire_time
}

output "id" {
  description = "returns a string"
  value       = google_compute_managed_ssl_certificate.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_managed_ssl_certificate.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_managed_ssl_certificate.this.self_link
}

output "subject_alternative_names" {
  description = "returns a list of string"
  value       = google_compute_managed_ssl_certificate.this.subject_alternative_names
}

output "this" {
  value = google_compute_managed_ssl_certificate.this
}
```

[top](#index)