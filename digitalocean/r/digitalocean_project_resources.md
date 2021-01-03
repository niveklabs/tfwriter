# digitalocean_project_resources

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_project_resources" {
  source = "./modules/digitalocean/r/digitalocean_project_resources"

  # project - (required) is a type of string
  project = null
  # resources - (required) is a type of set of string
  resources = []
}
```

[top](#index)

### Variables

```terraform
variable "project" {
  description = "(required) - project ID"
  type        = string
}

variable "resources" {
  description = "(required) - the resources associated with the project"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_project_resources" "this" {
  project   = var.project
  resources = var.resources
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_project_resources.this.id
}

output "this" {
  value = digitalocean_project_resources.this
}
```

[top](#index)