# launchdarkly_webhook

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
module "launchdarkly_webhook" {
  source = "./modules/launchdarkly/r/launchdarkly_webhook"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (optional) is a type of string
  name = null
  # secret - (optional) is a type of string
  secret = null
  # tags - (optional) is a type of set of string
  tags = []
  # url - (required) is a type of string
  url = null

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
variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
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
resource "launchdarkly_webhook" "this" {
  enabled = var.enabled
  name    = var.name
  secret  = var.secret
  tags    = var.tags
  url     = var.url

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
  value       = launchdarkly_webhook.this.id
}

output "this" {
  value = launchdarkly_webhook.this
}
```

[top](#index)