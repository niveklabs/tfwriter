# google_secret_manager_secret

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
module "google_secret_manager_secret" {
  source = "./modules/google/r/google_secret_manager_secret"

  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null
  # secret_id - (required) is a type of string
  secret_id = null

  replication = [{
    automatic = null
    user_managed = [{
      replicas = [{
        location = null
      }]
    }]
  }]

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
variable "labels" {
  description = "(optional) - The labels assigned to this Secret.\n\nLabel keys must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128 bytes,\nand must conform to the following PCRE regular expression: [\\p{Ll}\\p{Lo}][\\p{Ll}\\p{Lo}\\p{N}_-]{0,62}\n\nLabel values must be between 0 and 63 characters long, have a UTF-8 encoding of maximum 128 bytes,\nand must conform to the following PCRE regular expression: [\\p{Ll}\\p{Lo}\\p{N}_-]{0,63}\n\nNo more than 64 labels can be assigned to a given resource.\n\nAn object containing a list of \"key\": value pairs. Example:\n{ \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_id" {
  description = "(required) - This must be unique within the project."
  type        = string
}

variable "replication" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      automatic = bool
      user_managed = list(object(
        {
          replicas = list(object(
            {
              location = string
            }
          ))
        }
      ))
    }
  ))
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
resource "google_secret_manager_secret" "this" {
  # labels - (optional) is a type of map of string
  labels = var.labels
  # project - (optional) is a type of string
  project = var.project
  # secret_id - (required) is a type of string
  secret_id = var.secret_id

  dynamic "replication" {
    for_each = var.replication
    content {
      # automatic - (optional) is a type of bool
      automatic = replication.value["automatic"]

      dynamic "user_managed" {
        for_each = replication.value.user_managed
        content {

          dynamic "replicas" {
            for_each = user_managed.value.replicas
            content {
              # location - (required) is a type of string
              location = replicas.value["location"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_secret_manager_secret.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_secret_manager_secret.this.id
}

output "name" {
  description = "returns a string"
  value       = google_secret_manager_secret.this.name
}

output "project" {
  description = "returns a string"
  value       = google_secret_manager_secret.this.project
}

output "this" {
  value = google_secret_manager_secret.this
}
```

[top](#index)