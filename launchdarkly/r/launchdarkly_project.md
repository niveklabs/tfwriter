# launchdarkly_project

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_project" {
  source = "./modules/launchdarkly/r/launchdarkly_project"

  # include_in_snippet - (optional) is a type of bool
  include_in_snippet = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []

  environments = [{
    api_key              = null
    client_side_id       = null
    color                = null
    confirm_changes      = null
    default_track_events = null
    default_ttl          = null
    key                  = null
    mobile_key           = null
    name                 = null
    require_comments     = null
    secure_mode          = null
    tags                 = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "include_in_snippet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "environments" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      api_key              = string
      client_side_id       = string
      color                = string
      confirm_changes      = bool
      default_track_events = bool
      default_ttl          = number
      key                  = string
      mobile_key           = string
      name                 = string
      require_comments     = bool
      secure_mode          = bool
      tags                 = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_project" "this" {
  # include_in_snippet - (optional) is a type of bool
  include_in_snippet = var.include_in_snippet
  # key - (required) is a type of string
  key = var.key
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags

  dynamic "environments" {
    for_each = var.environments
    content {
      # color - (required) is a type of string
      color = environments.value["color"]
      # confirm_changes - (optional) is a type of bool
      confirm_changes = environments.value["confirm_changes"]
      # default_track_events - (optional) is a type of bool
      default_track_events = environments.value["default_track_events"]
      # default_ttl - (optional) is a type of number
      default_ttl = environments.value["default_ttl"]
      # key - (required) is a type of string
      key = environments.value["key"]
      # name - (required) is a type of string
      name = environments.value["name"]
      # require_comments - (optional) is a type of bool
      require_comments = environments.value["require_comments"]
      # secure_mode - (optional) is a type of bool
      secure_mode = environments.value["secure_mode"]
      # tags - (optional) is a type of set of string
      tags = environments.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = launchdarkly_project.this.id
}

output "this" {
  value = launchdarkly_project.this
}
```

[top](#index)