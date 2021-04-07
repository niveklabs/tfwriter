# rancher2_role_template

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_role_template" {
  source = "./modules/rancher2/r/rancher2_role_template"

  # administrative - (optional) is a type of bool
  administrative = null
  # annotations - (optional) is a type of map of string
  annotations = {}
  # context - (optional) is a type of string
  context = null
  # default_role - (optional) is a type of bool
  default_role = null
  # description - (optional) is a type of string
  description = null
  # external - (optional) is a type of bool
  external = null
  # hidden - (optional) is a type of bool
  hidden = null
  # labels - (optional) is a type of map of string
  labels = {}
  # locked - (optional) is a type of bool
  locked = null
  # name - (required) is a type of string
  name = null
  # role_template_ids - (optional) is a type of list of string
  role_template_ids = []

  rules = [{
    api_groups        = []
    non_resource_urls = []
    resource_names    = []
    resources         = []
    verbs             = []
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
variable "administrative" {
  description = "(optional) - Administrative role template"
  type        = bool
  default     = null
}

variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "context" {
  description = "(optional) - Context role template"
  type        = string
  default     = null
}

variable "default_role" {
  description = "(optional) - Default role template for new created cluster or project"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Role template policy description"
  type        = string
  default     = null
}

variable "external" {
  description = "(optional) - External role template"
  type        = bool
  default     = null
}

variable "hidden" {
  description = "(optional) - Hidden role template"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "locked" {
  description = "(optional) - Locked role template"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Role template policy name"
  type        = string
}

variable "role_template_ids" {
  description = "(optional) - Inherit role template IDs"
  type        = list(string)
  default     = null
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      api_groups        = list(string)
      non_resource_urls = list(string)
      resource_names    = list(string)
      resources         = list(string)
      verbs             = list(string)
    }
  ))
  default = []
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
resource "rancher2_role_template" "this" {
  # administrative - (optional) is a type of bool
  administrative = var.administrative
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # context - (optional) is a type of string
  context = var.context
  # default_role - (optional) is a type of bool
  default_role = var.default_role
  # description - (optional) is a type of string
  description = var.description
  # external - (optional) is a type of bool
  external = var.external
  # hidden - (optional) is a type of bool
  hidden = var.hidden
  # labels - (optional) is a type of map of string
  labels = var.labels
  # locked - (optional) is a type of bool
  locked = var.locked
  # name - (required) is a type of string
  name = var.name
  # role_template_ids - (optional) is a type of list of string
  role_template_ids = var.role_template_ids

  dynamic "rules" {
    for_each = var.rules
    content {
      # api_groups - (optional) is a type of list of string
      api_groups = rules.value["api_groups"]
      # non_resource_urls - (optional) is a type of list of string
      non_resource_urls = rules.value["non_resource_urls"]
      # resource_names - (optional) is a type of list of string
      resource_names = rules.value["resource_names"]
      # resources - (optional) is a type of list of string
      resources = rules.value["resources"]
      # verbs - (optional) is a type of list of string
      verbs = rules.value["verbs"]
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
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_role_template.this.annotations
}

output "builtin" {
  description = "returns a bool"
  value       = rancher2_role_template.this.builtin
}

output "description" {
  description = "returns a string"
  value       = rancher2_role_template.this.description
}

output "id" {
  description = "returns a string"
  value       = rancher2_role_template.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_role_template.this.labels
}

output "role_template_ids" {
  description = "returns a list of string"
  value       = rancher2_role_template.this.role_template_ids
}

output "this" {
  value = rancher2_role_template.this
}
```

[top](#index)