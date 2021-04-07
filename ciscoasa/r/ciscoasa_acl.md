# ciscoasa_acl

[back](../ciscoasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ciscoasa = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ciscoasa_acl" {
  source = "./modules/ciscoasa/r/ciscoasa_acl"

  # name - (required) is a type of string
  name = null

  rule = [{
    active              = null
    destination         = null
    destination_service = null
    id                  = null
    log_interval        = null
    log_status          = null
    permit              = null
    remarks             = []
    source              = null
    source_service      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      active              = bool
      destination         = string
      destination_service = string
      id                  = string
      log_interval        = number
      log_status          = string
      permit              = bool
      remarks             = list(string)
      source              = string
      source_service      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "ciscoasa_acl" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      # active - (optional) is a type of bool
      active = rule.value["active"]
      # destination - (required) is a type of string
      destination = rule.value["destination"]
      # destination_service - (required) is a type of string
      destination_service = rule.value["destination_service"]
      # log_interval - (optional) is a type of number
      log_interval = rule.value["log_interval"]
      # log_status - (optional) is a type of string
      log_status = rule.value["log_status"]
      # permit - (optional) is a type of bool
      permit = rule.value["permit"]
      # remarks - (optional) is a type of list of string
      remarks = rule.value["remarks"]
      # source - (required) is a type of string
      source = rule.value["source"]
      # source_service - (optional) is a type of string
      source_service = rule.value["source_service"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ciscoasa_acl.this.id
}

output "this" {
  value = ciscoasa_acl.this
}
```

[top](#index)