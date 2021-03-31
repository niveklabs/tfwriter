# google_os_login_ssh_public_key

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
module "google_os_login_ssh_public_key" {
  source = "./modules/google/r/google_os_login_ssh_public_key"

  # expiration_time_usec - (optional) is a type of string
  expiration_time_usec = null
  # key - (required) is a type of string
  key = null
  # project - (optional) is a type of string
  project = null
  # user - (required) is a type of string
  user = null

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
variable "expiration_time_usec" {
  description = "(optional) - An expiration time in microseconds since epoch."
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - Public key text in SSH format, defined by RFC4253 section 6.6."
  type        = string
}

variable "project" {
  description = "(optional) - The project ID of the Google Cloud Platform project."
  type        = string
  default     = null
}

variable "user" {
  description = "(required) - The user email."
  type        = string
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
resource "google_os_login_ssh_public_key" "this" {
  expiration_time_usec = var.expiration_time_usec
  key                  = var.key
  project              = var.project
  user                 = var.user

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
output "fingerprint" {
  description = "returns a string"
  value       = google_os_login_ssh_public_key.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_os_login_ssh_public_key.this.id
}

output "this" {
  value = google_os_login_ssh_public_key.this
}
```

[top](#index)