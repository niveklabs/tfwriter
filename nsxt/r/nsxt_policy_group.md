# nsxt_policy_group

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_group" {
  source = "./modules/nsxt/r/nsxt_policy_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # nsx_id - (optional) is a type of string
  nsx_id = null

  conjunction = [{
    operator = null
  }]

  criteria = [{
    condition = [{
      key         = null
      member_type = null
      operator    = null
      value       = null
    }]
    ipaddress_expression = [{
      ip_addresses = []
    }]
    macaddress_expression = [{
      mac_addresses = []
    }]
    path_expression = [{
      member_paths = []
    }]
  }]

  extended_criteria = [{
    identity_group = [{
      distinguished_name             = null
      domain_base_distinguished_name = null
      sid                            = null
    }]
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "domain" {
  description = "(optional) - The domain name to use for resources. If not specified 'default' is used"
  type        = string
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "conjunction" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      operator = string
    }
  ))
  default = []
}

variable "criteria" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      condition = list(object(
        {
          key         = string
          member_type = string
          operator    = string
          value       = string
        }
      ))
      ipaddress_expression = list(object(
        {
          ip_addresses = set(string)
        }
      ))
      macaddress_expression = list(object(
        {
          mac_addresses = set(string)
        }
      ))
      path_expression = list(object(
        {
          member_paths = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "extended_criteria" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_group = set(object(
        {
          distinguished_name             = string
          domain_base_distinguished_name = string
          sid                            = string
        }
      ))
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_group" "this" {
  description  = var.description
  display_name = var.display_name
  domain       = var.domain
  nsx_id       = var.nsx_id

  dynamic "conjunction" {
    for_each = var.conjunction
    content {
      operator = conjunction.value["operator"]
    }
  }

  dynamic "criteria" {
    for_each = var.criteria
    content {

      dynamic "condition" {
        for_each = criteria.value.condition
        content {
          key         = condition.value["key"]
          member_type = condition.value["member_type"]
          operator    = condition.value["operator"]
          value       = condition.value["value"]
        }
      }

      dynamic "ipaddress_expression" {
        for_each = criteria.value.ipaddress_expression
        content {
          ip_addresses = ipaddress_expression.value["ip_addresses"]
        }
      }

      dynamic "macaddress_expression" {
        for_each = criteria.value.macaddress_expression
        content {
          mac_addresses = macaddress_expression.value["mac_addresses"]
        }
      }

      dynamic "path_expression" {
        for_each = criteria.value.path_expression
        content {
          member_paths = path_expression.value["member_paths"]
        }
      }

    }
  }

  dynamic "extended_criteria" {
    for_each = var.extended_criteria
    content {

      dynamic "identity_group" {
        for_each = extended_criteria.value.identity_group
        content {
          distinguished_name             = identity_group.value["distinguished_name"]
          domain_base_distinguished_name = identity_group.value["domain_base_distinguished_name"]
          sid                            = identity_group.value["sid"]
        }
      }

    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_group.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_group.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_group.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_group.this.revision
}

output "this" {
  value = nsxt_policy_group.this
}
```

[top](#index)