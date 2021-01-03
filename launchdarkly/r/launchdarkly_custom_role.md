# launchdarkly_custom_role

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
    launchdarkly = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_custom_role" {
  source = "./modules/launchdarkly/r/launchdarkly_custom_role"

  # description - (optional) is a type of string
  description = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null

  policy = [{
    actions   = []
    effect    = null
    resources = []
  }]

  policy_statements = [{
    actions       = []
    effect        = null
    not_actions   = []
    not_resources = []
    resources     = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
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

variable "policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      actions   = list(string)
      effect    = string
      resources = list(string)
    }
  ))
  default = []
}

variable "policy_statements" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      actions       = list(string)
      effect        = string
      not_actions   = list(string)
      not_resources = list(string)
      resources     = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_custom_role" "this" {
  description = var.description
  key         = var.key
  name        = var.name

  dynamic "policy" {
    for_each = var.policy
    content {
      actions   = policy.value["actions"]
      effect    = policy.value["effect"]
      resources = policy.value["resources"]
    }
  }

  dynamic "policy_statements" {
    for_each = var.policy_statements
    content {
      actions       = policy_statements.value["actions"]
      effect        = policy_statements.value["effect"]
      not_actions   = policy_statements.value["not_actions"]
      not_resources = policy_statements.value["not_resources"]
      resources     = policy_statements.value["resources"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = launchdarkly_custom_role.this.id
}

output "this" {
  value = launchdarkly_custom_role.this
}
```

[top](#index)