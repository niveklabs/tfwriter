# google_data_catalog_taxonomy

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
module "google_data_catalog_taxonomy" {
  source = "./modules/google-beta/r/google_data_catalog_taxonomy"

  # activated_policy_types - (optional) is a type of list of string
  activated_policy_types = []
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

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
variable "activated_policy_types" {
  description = "(optional) - A list of policy types that are activated for this taxonomy. If not set,\ndefaults to an empty list. Possible values: [\"POLICY_TYPE_UNSPECIFIED\", \"FINE_GRAINED_ACCESS_CONTROL\"]"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of this taxonomy. It must: contain only unicode characters,\ntabs, newlines, carriage returns and page breaks; and be at most 2000 bytes\nlong when encoded in UTF-8. If not set, defaults to an empty description."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - User defined name of this taxonomy.\nIt must: contain only unicode letters, numbers, underscores, dashes\nand spaces; not start or end with spaces; and be at most 200 bytes\nlong when encoded in UTF-8."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Taxonomy location region."
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
resource "google_data_catalog_taxonomy" "this" {
  activated_policy_types = var.activated_policy_types
  description            = var.description
  display_name           = var.display_name
  project                = var.project
  region                 = var.region

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
  value       = google_data_catalog_taxonomy.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy.this.name
}

output "project" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy.this.region
}

output "this" {
  value = google_data_catalog_taxonomy.this
}
```

[top](#index)