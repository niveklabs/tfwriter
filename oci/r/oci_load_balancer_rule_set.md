# oci_load_balancer_rule_set

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_rule_set" {
  source = "./modules/oci/r/oci_load_balancer_rule_set"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null

  items = [{
    action                         = null
    allowed_methods                = []
    are_invalid_characters_allowed = null
    conditions = [{
      attribute_name  = null
      attribute_value = null
      operator        = null
    }]
    description                  = null
    header                       = null
    http_large_header_size_in_kb = null
    prefix                       = null
    redirect_uri = [{
      host     = null
      path     = null
      port     = null
      protocol = null
      query    = null
    }]
    response_code = null
    status_code   = null
    suffix        = null
    value         = null
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
variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "items" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      action                         = string
      allowed_methods                = set(string)
      are_invalid_characters_allowed = bool
      conditions = list(object(
        {
          attribute_name  = string
          attribute_value = string
          operator        = string
        }
      ))
      description                  = string
      header                       = string
      http_large_header_size_in_kb = number
      prefix                       = string
      redirect_uri = list(object(
        {
          host     = string
          path     = string
          port     = number
          protocol = string
          query    = string
        }
      ))
      response_code = number
      status_code   = number
      suffix        = string
      value         = string
    }
  ))
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
resource "oci_load_balancer_rule_set" "this" {
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id
  # name - (required) is a type of string
  name = var.name

  dynamic "items" {
    for_each = var.items
    content {
      # action - (required) is a type of string
      action = items.value["action"]
      # allowed_methods - (optional) is a type of set of string
      allowed_methods = items.value["allowed_methods"]
      # are_invalid_characters_allowed - (optional) is a type of bool
      are_invalid_characters_allowed = items.value["are_invalid_characters_allowed"]
      # description - (optional) is a type of string
      description = items.value["description"]
      # header - (optional) is a type of string
      header = items.value["header"]
      # http_large_header_size_in_kb - (optional) is a type of number
      http_large_header_size_in_kb = items.value["http_large_header_size_in_kb"]
      # prefix - (optional) is a type of string
      prefix = items.value["prefix"]
      # response_code - (optional) is a type of number
      response_code = items.value["response_code"]
      # status_code - (optional) is a type of number
      status_code = items.value["status_code"]
      # suffix - (optional) is a type of string
      suffix = items.value["suffix"]
      # value - (optional) is a type of string
      value = items.value["value"]

      dynamic "conditions" {
        for_each = items.value.conditions
        content {
          # attribute_name - (required) is a type of string
          attribute_name = conditions.value["attribute_name"]
          # attribute_value - (required) is a type of string
          attribute_value = conditions.value["attribute_value"]
          # operator - (optional) is a type of string
          operator = conditions.value["operator"]
        }
      }

      dynamic "redirect_uri" {
        for_each = items.value.redirect_uri
        content {
          # host - (optional) is a type of string
          host = redirect_uri.value["host"]
          # path - (optional) is a type of string
          path = redirect_uri.value["path"]
          # port - (optional) is a type of number
          port = redirect_uri.value["port"]
          # protocol - (optional) is a type of string
          protocol = redirect_uri.value["protocol"]
          # query - (optional) is a type of string
          query = redirect_uri.value["query"]
        }
      }

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
output "id" {
  description = "returns a string"
  value       = oci_load_balancer_rule_set.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_rule_set.this.state
}

output "this" {
  value = oci_load_balancer_rule_set.this
}
```

[top](#index)