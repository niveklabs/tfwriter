# google_scc_source

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
module "google_scc_source" {
  source = "./modules/google-beta/r/google_scc_source"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # organization - (required) is a type of string
  organization = null

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
  description = "(optional) - The description of the source (max of 1024 characters)."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - The source’s display name. A source’s display name must be unique\namongst its siblings, for example, two sources with the same parent\ncan't share the same display name. The display name must start and end\nwith a letter or digit, may contain letters, digits, spaces, hyphens,\nand underscores, and can be no longer than 32 characters."
  type        = string
}

variable "organization" {
  description = "(required) - The organization whose Cloud Security Command Center the Source\nlives in."
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
resource "google_scc_source" "this" {
  description  = var.description
  display_name = var.display_name
  organization = var.organization

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
  value       = google_scc_source.this.id
}

output "name" {
  description = "returns a string"
  value       = google_scc_source.this.name
}

output "this" {
  value = google_scc_source.this
}
```

[top](#index)