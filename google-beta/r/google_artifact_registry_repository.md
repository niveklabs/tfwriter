# google_artifact_registry_repository

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_artifact_registry_repository" {
  source = "./modules/google-beta/r/google_artifact_registry_repository"

  # description - (optional) is a type of string
  description = null
  # format - (required) is a type of string
  format = null
  # kms_key_name - (optional) is a type of string
  kms_key_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
  # repository_id - (required) is a type of string
  repository_id = null

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
variable "description" {
  description = "(optional) - The user-provided description of the repository."
  type        = string
  default     = null
}

variable "format" {
  description = "(required) - The format of packages that are stored in the repository. Possible values: [\"DOCKER\"]"
  type        = string
}

variable "kms_key_name" {
  description = "(optional) - The Cloud KMS resource name of the customer managed encryption key that’s\nused to encrypt the contents of the Repository. Has the form:\n'projects/my-project/locations/my-region/keyRings/my-kr/cryptoKeys/my-key'.\nThis value may not be changed after the Repository has been created."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels with user-defined metadata.\nThis field may contain up to 64 entries. Label keys and values may be no\nlonger than 63 characters. Label keys must begin with a lowercase letter\nand may only contain lowercase letters, numeric characters, underscores,\nand dashes."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - The name of the location this repository is located in."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository_id" {
  description = "(required) - The last part of the repository name, for example:\n\"repo1\""
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
resource "google_artifact_registry_repository" "this" {
  description   = var.description
  format        = var.format
  kms_key_name  = var.kms_key_name
  labels        = var.labels
  location      = var.location
  project       = var.project
  repository_id = var.repository_id

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
output "create_time" {
  description = "returns a string"
  value       = google_artifact_registry_repository.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_artifact_registry_repository.this.id
}

output "location" {
  description = "returns a string"
  value       = google_artifact_registry_repository.this.location
}

output "name" {
  description = "returns a string"
  value       = google_artifact_registry_repository.this.name
}

output "project" {
  description = "returns a string"
  value       = google_artifact_registry_repository.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_artifact_registry_repository.this.update_time
}

output "this" {
  value = google_artifact_registry_repository.this
}
```

[top](#index)