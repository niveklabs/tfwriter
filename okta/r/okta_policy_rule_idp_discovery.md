# okta_policy_rule_idp_discovery

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_policy_rule_idp_discovery" {
  source = "./modules/okta/r/okta_policy_rule_idp_discovery"

  # idp_id - (optional) is a type of string
  idp_id = null
  # idp_type - (optional) is a type of string
  idp_type = null
  # name - (required) is a type of string
  name = null
  # network_connection - (optional) is a type of string
  network_connection = null
  # network_excludes - (optional) is a type of list of string
  network_excludes = []
  # network_includes - (optional) is a type of list of string
  network_includes = []
  # policyid - (required) is a type of string
  policyid = null
  # priority - (optional) is a type of number
  priority = null
  # status - (optional) is a type of string
  status = null
  # user_identifier_attribute - (optional) is a type of string
  user_identifier_attribute = null
  # user_identifier_type - (optional) is a type of string
  user_identifier_type = null

  app_exclude = [{
    id   = null
    name = null
    type = null
  }]

  app_include = [{
    id   = null
    name = null
    type = null
  }]

  platform_include = [{
    os_expression = null
    os_type       = null
    type          = null
  }]

  user_identifier_patterns = [{
    match_type = null
    value      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "idp_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Policy Rule Name"
  type        = string
}

variable "network_connection" {
  description = "(optional) - Network selection mode: ANYWHERE, ZONE, ON_NETWORK, or OFF_NETWORK."
  type        = string
  default     = null
}

variable "network_excludes" {
  description = "(optional) - The zones to exclude"
  type        = list(string)
  default     = null
}

variable "network_includes" {
  description = "(optional) - The zones to include"
  type        = list(string)
  default     = null
}

variable "policyid" {
  description = "(required) - Policy ID of the Rule"
  type        = string
}

variable "priority" {
  description = "(optional) - Policy Rule Priority, this attribute can be set to a valid priority. To avoid endless diff situation we error if an invalid priority is provided. API defaults it to the last (lowest) if not there."
  type        = number
  default     = null
}

variable "status" {
  description = "(optional) - Policy Rule Status: ACTIVE or INACTIVE."
  type        = string
  default     = null
}

variable "user_identifier_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_identifier_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_exclude" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
      type = string
    }
  ))
  default = []
}

variable "app_include" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
      type = string
    }
  ))
  default = []
}

variable "platform_include" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      os_expression = string
      os_type       = string
      type          = string
    }
  ))
  default = []
}

variable "user_identifier_patterns" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      match_type = string
      value      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_policy_rule_idp_discovery" "this" {
  # idp_id - (optional) is a type of string
  idp_id = var.idp_id
  # idp_type - (optional) is a type of string
  idp_type = var.idp_type
  # name - (required) is a type of string
  name = var.name
  # network_connection - (optional) is a type of string
  network_connection = var.network_connection
  # network_excludes - (optional) is a type of list of string
  network_excludes = var.network_excludes
  # network_includes - (optional) is a type of list of string
  network_includes = var.network_includes
  # policyid - (required) is a type of string
  policyid = var.policyid
  # priority - (optional) is a type of number
  priority = var.priority
  # status - (optional) is a type of string
  status = var.status
  # user_identifier_attribute - (optional) is a type of string
  user_identifier_attribute = var.user_identifier_attribute
  # user_identifier_type - (optional) is a type of string
  user_identifier_type = var.user_identifier_type

  dynamic "app_exclude" {
    for_each = var.app_exclude
    content {
      # id - (optional) is a type of string
      id = app_exclude.value["id"]
      # name - (optional) is a type of string
      name = app_exclude.value["name"]
      # type - (required) is a type of string
      type = app_exclude.value["type"]
    }
  }

  dynamic "app_include" {
    for_each = var.app_include
    content {
      # id - (optional) is a type of string
      id = app_include.value["id"]
      # name - (optional) is a type of string
      name = app_include.value["name"]
      # type - (required) is a type of string
      type = app_include.value["type"]
    }
  }

  dynamic "platform_include" {
    for_each = var.platform_include
    content {
      # os_expression - (optional) is a type of string
      os_expression = platform_include.value["os_expression"]
      # os_type - (optional) is a type of string
      os_type = platform_include.value["os_type"]
      # type - (optional) is a type of string
      type = platform_include.value["type"]
    }
  }

  dynamic "user_identifier_patterns" {
    for_each = var.user_identifier_patterns
    content {
      # match_type - (optional) is a type of string
      match_type = user_identifier_patterns.value["match_type"]
      # value - (optional) is a type of string
      value = user_identifier_patterns.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_policy_rule_idp_discovery.this.id
}

output "this" {
  value = okta_policy_rule_idp_discovery.this
}
```

[top](#index)