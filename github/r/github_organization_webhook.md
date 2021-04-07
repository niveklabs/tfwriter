# github_organization_webhook

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_organization_webhook" {
  source = "./modules/github/r/github_organization_webhook"

  # active - (optional) is a type of bool
  active = null
  # events - (required) is a type of set of string
  events = []
  # name - (optional) is a type of string
  name = null

  configuration = [{
    content_type = null
    insecure_ssl = null
    secret       = null
    url          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "events" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_type = string
      insecure_ssl = bool
      secret       = string
      url          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "github_organization_webhook" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # events - (required) is a type of set of string
  events = var.events
  # name - (optional) is a type of string
  name = var.name

  dynamic "configuration" {
    for_each = var.configuration
    content {
      # content_type - (optional) is a type of string
      content_type = configuration.value["content_type"]
      # insecure_ssl - (optional) is a type of bool
      insecure_ssl = configuration.value["insecure_ssl"]
      # secret - (optional) is a type of string
      secret = configuration.value["secret"]
      # url - (required) is a type of string
      url = configuration.value["url"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_organization_webhook.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_organization_webhook.this.id
}

output "url" {
  description = "returns a string"
  value       = github_organization_webhook.this.url
}

output "this" {
  value = github_organization_webhook.this
}
```

[top](#index)