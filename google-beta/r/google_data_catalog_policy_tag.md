# google_data_catalog_policy_tag

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
module "google_data_catalog_policy_tag" {
  source = "./modules/google-beta/r/google_data_catalog_policy_tag"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # parent_policy_tag - (optional) is a type of string
  parent_policy_tag = null
  # taxonomy - (required) is a type of string
  taxonomy = null

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
  description = "(optional) - Description of this policy tag. It must: contain only unicode characters, tabs,\nnewlines, carriage returns and page breaks; and be at most 2000 bytes long when\nencoded in UTF-8. If not set, defaults to an empty description.\nIf not set, defaults to an empty description."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - User defined name of this policy tag. It must: be unique within the parent\ntaxonomy; contain only unicode letters, numbers, underscores, dashes and spaces;\nnot start or end with spaces; and be at most 200 bytes long when encoded in UTF-8."
  type        = string
}

variable "parent_policy_tag" {
  description = "(optional) - Resource name of this policy tag's parent policy tag.\nIf empty, it means this policy tag is a top level policy tag.\nIf not set, defaults to an empty string."
  type        = string
  default     = null
}

variable "taxonomy" {
  description = "(required) - Taxonomy the policy tag is associated with"
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
resource "google_data_catalog_policy_tag" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # parent_policy_tag - (optional) is a type of string
  parent_policy_tag = var.parent_policy_tag
  # taxonomy - (required) is a type of string
  taxonomy = var.taxonomy

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
output "child_policy_tags" {
  description = "returns a list of string"
  value       = google_data_catalog_policy_tag.this.child_policy_tags
}

output "id" {
  description = "returns a string"
  value       = google_data_catalog_policy_tag.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_catalog_policy_tag.this.name
}

output "this" {
  value = google_data_catalog_policy_tag.this
}
```

[top](#index)